![image](https://github.com/user-attachments/assets/e0b424f1-0b47-4e37-bcd9-7e5bb16d0115)
![image](https://github.com/user-attachments/assets/b6045d52-19d0-4c49-9b9a-17d056070b44)
![image](https://github.com/user-attachments/assets/dfe72c74-4d55-44f8-9174-e4ccfc0aeb44)
![image](https://github.com/user-attachments/assets/5f1afa0c-8aac-41a9-9ffe-d0d06c439d03)
![image](https://github.com/user-attachments/assets/62767224-efd5-478a-aebe-1c3442f19055)
![image](https://github.com/user-attachments/assets/a7d50abc-d6b2-4d53-9c36-fc8a62667034)
![image](https://github.com/user-attachments/assets/ef0fb06b-5cb7-4415-921b-4520d925554f)
![image](https://github.com/user-attachments/assets/25a1f58f-87e0-402f-b9e9-c2ee6fc46b6e)
![image](https://github.com/user-attachments/assets/fecba2ce-f721-4c6a-9636-062bbb4a8721)
![image](https://github.com/user-attachments/assets/0671a1d2-c39b-4ba4-b49c-311c1ca16c6b)
![image](https://github.com/user-attachments/assets/6646183b-218c-46ca-8f46-93a39f35761f)
![image](https://github.com/user-attachments/assets/84dd4dcd-abf2-4c2c-96a7-23ef1fb9097a)
![image](https://github.com/user-attachments/assets/2f8cd46c-b6fd-4f7a-a1fb-ed67721f5ebf)
![image](https://github.com/user-attachments/assets/15360adb-e694-48b1-842d-ef6fa37f2f2e)
![image](https://github.com/user-attachments/assets/be0e324f-157d-4ad8-9893-d2faacfc0edb)
![image](https://github.com/user-attachments/assets/909786d9-36cf-4f14-96de-2b6e8682112f)
![image](https://github.com/user-attachments/assets/4c3ac75e-5b3f-44c5-ab24-1580cc75f835)
![image](https://github.com/user-attachments/assets/c0b1e4dd-9d82-4b56-a694-f582b2b683e0)
![image](https://github.com/user-attachments/assets/55d5b593-a50d-4fff-9d0f-030fdc48f592)
![image](https://github.com/user-attachments/assets/5b05b0c7-5a6d-49a8-8a0b-4a39f7bf8a46)
![image](https://github.com/user-attachments/assets/3f7092d3-1e57-473d-b2d9-c3a5d0c3f470)
![image](https://github.com/user-attachments/assets/582aad0f-bbeb-4711-bda7-42f19345497d)
![image](https://github.com/user-attachments/assets/d47a81a4-e5ae-4dd5-9807-8db69e3163fe)
![image](https://github.com/user-attachments/assets/efedfaec-7ab3-48aa-9d1d-d44ef0ce59ef)
![image](https://github.com/user-attachments/assets/8cd2bdb0-93d5-4a20-ab83-2458e4dd987b)
![image](https://github.com/user-attachments/assets/3de7d264-703e-45b4-998a-bc3796265e4c)
![image](https://github.com/user-attachments/assets/8851f78a-ea8f-43f3-81d2-e82ba0304c31)
![image](https://github.com/user-attachments/assets/dc7133d5-824b-405c-8815-ec823935dcbb)
![image](https://github.com/user-attachments/assets/7d215f44-57ef-4b2b-85b4-d6a98ef20a7b)
![image](https://github.com/user-attachments/assets/f737efd6-40a1-4906-be8f-698a616ac79c)
![image](https://github.com/user-attachments/assets/c81bb572-e34c-4a59-8ff0-748c03cb8b09)
![image](https://github.com/user-attachments/assets/d201160d-4a32-4425-8502-9f0c70f07db3)


1. first nmap -p-    only port 22 and 80 open

2. brute force directly -- get local.txt

3. cannot get entry point, second nmap -p-     get port 6789 open

4. brute force directory :6789    got files, terminal, etc.

5. termial --> exeucte commands

6. linpeas, port 3306, 10050,10051 etc. open, interesting file /etc/zabbix/web/zabbix.conf.php

7. get mysql username and password from /etc/zabbix/web/zabbix.conf.php

8. mysql, get admin username and hash --> john, get password

9. http://zab.local/zabbix --> cannot access (under maintenance)
  
10. as port 10050, 10051 (zabbix) open on local 127.0.0.1, on machine terminal, curl 127.0.0.1/zabbix --> Moved Permanently, Port 80

11. SSH Remote Port Forwarding --> forward local port 80 to Kali port 80

12. Open Kali browser 127.0.0.1/zabbix, get login portal

13. login with username and password obtained from MySQL database (Admin:dinosaur   case sensitive)

14. Alerts --> Scripts --> Create Script --> create reverse shell

15. Monitor --> Hosts --> Zabbix server --> click on the created shell --> error

16. base64 encode reverse shell, update command to "echo <base64-encoded-shell> | base64 -d | /bin/bash"

17. get reverse shell, user zabbix --> sudo -l --> GTFOBins rsync --> PE to root
