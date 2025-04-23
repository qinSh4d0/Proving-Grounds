![image](https://github.com/user-attachments/assets/17535866-c6d7-419f-be63-3cdb1b31758a)
![image](https://github.com/user-attachments/assets/546e4934-bcb9-4092-bdee-1c2f8b177c02)
![image](https://github.com/user-attachments/assets/817fae93-4b53-494d-a413-0f94035e4eba)
![image](https://github.com/user-attachments/assets/36bc1a91-7763-458a-afc1-394daf10c49b)
![image](https://github.com/user-attachments/assets/ca2495da-d283-4cf0-be2f-7c2e9e02aa6b)
![image](https://github.com/user-attachments/assets/ec0dded8-3bdc-4186-b5c8-5e76c23c1f84)
![image](https://github.com/user-attachments/assets/e80a133b-d4de-4471-a4a1-0457f4b2b26c)
![image](https://github.com/user-attachments/assets/686ebbde-9a8c-48cf-b134-b3e8fdb7e7be)
![image](https://github.com/user-attachments/assets/373ffb9d-3233-4ea2-8316-0389f3815a5c)
![image](https://github.com/user-attachments/assets/b37d36bc-456a-406a-9070-2acf7c390b9b)
![image](https://github.com/user-attachments/assets/a915c78f-27b4-4a46-a102-3ca0f38d0407)
![image](https://github.com/user-attachments/assets/165646c2-effe-4bf2-b8b6-22fbc0bfed19)
![image](https://github.com/user-attachments/assets/8412008b-38f1-48ef-9802-cb3bb99d3f46)
![image](https://github.com/user-attachments/assets/d05e3250-8ae8-47c3-9293-db3b0fae6cee)
![image](https://github.com/user-attachments/assets/b700161f-6f38-4dc0-b9f7-c62192d765c1)
![image](https://github.com/user-attachments/assets/ca348e84-e9d7-44a0-b9ea-4ffd10c4bbf9)
![image](https://github.com/user-attachments/assets/9d9a242a-323b-4ea8-bfe3-06e2cf812fcf)
![image](https://github.com/user-attachments/assets/e3754796-f5bd-43ca-8a7a-022e3b93ac92)
![image](https://github.com/user-attachments/assets/f1df26ad-f4d9-4fa2-b16c-755dcdbc4864)
![image](https://github.com/user-attachments/assets/c7214d17-c59f-4c77-9b92-89ecc6676914)
![image](https://github.com/user-attachments/assets/0352083f-f242-4138-8548-b2beeb016740)
![image](https://github.com/user-attachments/assets/5cedb4dd-e33e-44db-ad9c-9ecce5aa9f84)
![image](https://github.com/user-attachments/assets/7f6eb3e8-50b1-403b-87b3-c4ac931c63b7)
![image](https://github.com/user-attachments/assets/77d8774a-2064-4ac0-b773-4dc995eb0126)
![image](https://github.com/user-attachments/assets/52ff1e3a-0d6f-4a4a-8e56-bf6ce48e4a62)
![image](https://github.com/user-attachments/assets/116c62db-ba21-4717-b702-068de9cfaa07)
![image](https://github.com/user-attachments/assets/0ccc6e4c-ef9d-4a5b-9a77-2cce1f9f6257)

1. whatweb --> Apache, Win64, OpenSSL, PHP  ---> most likely XAMPP

2. directory --> .php, /uploads/

3. file upload --> .php, .pHP, .php5, .php7, etc. prohibited

4. .htaccess  --> "AppType application/x-httpd-php .jpg/.evil/.dork etc."  -- allow creation of PHP extensions

5. Online Reverse Shell Generator -- Windows -- PHP Ivan Sincek (works on Windows OS) -- rename to .jpg or .evil or .dork

6. upload both .htaccess & PHP payload

7. trigger payload (browser or curl)

8. get reverse shell -- net users, PowerView.ps1 --> user svc_mssql is configured with SPN (serviceprincipalname)

9. Rubeus.exe --> get hash --> crack hash

10. netexec smb/winrm --> svc_mssql not admin (no Pwned!)

11. Run-As --> upload, import, & run --> confirm can escalate to user svc_mssql

12. systeminfo --> x64-based PC --> upload nc64.exe, Run-As --> reverse shell as svc_mssql

13. svc_mssql --> whoami /priv --> SeMachineAccountPrivilege, SeManageVolumePrivlege

14. SeManageVolumePrivilege --> google abuse --> "Get full control over C:\ when the user has SeManageVolumePrivilege (allowing to read/write any files). One possible way to get a shell from here is to write a custom dll to C:\Windows\System32\wbem\tzres.dll & call systeminfo to trigger it."

15. get SeManageVolumeExploit.exe and upload to machine --> Run the executate --> can write to C:\ drive

16. msfvenom generate payload tzres.dll, upload to C:\Windows\System32\wbem --> call systeminfo --> PrivEsc

17. Can also PE to SYSTEM by WerTrigger

![image](https://github.com/user-attachments/assets/3449dda8-3ed8-4961-8e69-3a1682ec4407)
![image](https://github.com/user-attachments/assets/7169dc49-9f38-4277-bf36-fe7473f33ab9)
![image](https://github.com/user-attachments/assets/ee001663-55be-473f-836f-68cf5f6cd5c5)
![image](https://github.com/user-attachments/assets/5f4abe83-1305-4478-b9cf-5f164e0d4a7e)
![image](https://github.com/user-attachments/assets/7b314d4e-7c06-48fb-b09c-1f6acde2649d)


