![image](https://github.com/user-attachments/assets/7c409217-caef-4442-8e6f-2f9cd653a080)
![image](https://github.com/user-attachments/assets/6438d7a6-0802-4a31-a6ed-87a4e5237574)
![image](https://github.com/user-attachments/assets/bebd2b16-fa0d-4c7c-8d97-676af40fb995)
![image](https://github.com/user-attachments/assets/f3f19973-ab1a-4270-ade1-b5b7a3ba2250)
![image](https://github.com/user-attachments/assets/2c41857c-8978-45bb-91d4-1e4da37e70ac)
![image](https://github.com/user-attachments/assets/8dcab6be-279f-47e0-bb2d-f6a5e2122515)
![image](https://github.com/user-attachments/assets/b83d4cd8-01f6-4df9-908b-9b9d645f9007)
![image](https://github.com/user-attachments/assets/4601101f-889f-4830-ba68-14f47dcf6034)
![image](https://github.com/user-attachments/assets/ebe3f97a-65b5-44bf-a91b-ad4e87062033)
![image](https://github.com/user-attachments/assets/10f19da7-8970-4007-8991-65ce35d39bb3)
![image](https://github.com/user-attachments/assets/cb791ed6-9988-4d45-ba66-58515997914f)
![image](https://github.com/user-attachments/assets/ab6fa9ed-1306-4f78-ab57-15c4520ed900)
![image](https://github.com/user-attachments/assets/02af9fd0-cffd-4759-bc3a-4f5d5fe570a8)
![image](https://github.com/user-attachments/assets/da97b7f7-86f3-40d7-acfe-23fe58cf78c4)

![image](https://github.com/user-attachments/assets/65fbaf38-7d00-4c46-bf34-960474edd46d)
![image](https://github.com/user-attachments/assets/67d20cbd-e427-4ab1-bd8f-2d1f8c4550d8)
![image](https://github.com/user-attachments/assets/7e6365e6-b533-4a62-8ef9-3a9a58d1aeaf)
![image](https://github.com/user-attachments/assets/9686a81e-78de-451d-8d43-5bc94799a4f7)
![image](https://github.com/user-attachments/assets/7e054bc2-1548-420e-961c-920f568cd4df)
![image](https://github.com/user-attachments/assets/2e39e49c-9da0-4ee3-a500-515574d5fb9b)
![image](https://github.com/user-attachments/assets/68caba70-48a5-42b7-aaea-0ef82ba0515f)
![image](https://github.com/user-attachments/assets/c55e8ce9-080f-4bb6-a11d-2898870e546a)
![image](https://github.com/user-attachments/assets/6c9a56c0-c9f1-4a13-8b01-62b3ef0d8a90)

![image](https://github.com/user-attachments/assets/99f0f04a-8980-436d-94e1-3c14ca22b43e)

![image](https://github.com/user-attachments/assets/1d61b30e-a400-462b-97d5-77eb929d8fcc)
![image](https://github.com/user-attachments/assets/78757369-a131-43f6-8edc-d91452179f61)
![image](https://github.com/user-attachments/assets/3d81c767-086c-4335-8313-05acd2e4f131)
![image](https://github.com/user-attachments/assets/6c479e96-eb99-480a-a32c-1a4606e897f8)


1. H2 Database default creds: sa:"" (password blank)

2. Run Exploit-DB 49384 three commands one by one --> the 3rd one "whoami" confirm user
   
3. systeminfo --> x64-based PC ---> upload nc64.exe & get reverse shell

4. first get reverse shell, basic commands get "Command not found" error --> %PATH% environment variable not set with good defauts.
   
   ```bash
   set PATH=%PATH%C:\Windows\System32;C:\Windows\System32\WindowsPowerShell\v1.0;
   ``` 

6. whoami /priv --> SeImpersionatePrivilege Enabled

7. Try various Potato.exe  ---> SharpEfsPotato.exe work ---> PE to SYSTEM
