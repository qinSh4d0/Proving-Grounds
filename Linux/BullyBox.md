![image](https://github.com/user-attachments/assets/55e046b0-7f1d-4d2d-9536-8c107aa50d32)
![image](https://github.com/user-attachments/assets/a9dcdf34-7010-4556-94cd-b0bcf71be4a1)
![image](https://github.com/user-attachments/assets/1644d9c7-e172-4606-808b-67fcd0b2798b)
![image](https://github.com/user-attachments/assets/d89a4134-6cb4-4278-8cb6-6e0e5789a133)
![image](https://github.com/user-attachments/assets/34eab6e3-4b72-4083-b0df-3dfc236248df)
![image](https://github.com/user-attachments/assets/5b1d8ddb-2594-4075-8f84-836d986b2deb)
![image](https://github.com/user-attachments/assets/44083176-6b0d-456b-b8bd-233af2e79676)
![image](https://github.com/user-attachments/assets/b796da83-ecf6-4d35-990c-522635702597)
![image](https://github.com/user-attachments/assets/bf119a58-7ed8-4a0c-a6ed-230943e6ea7d)
![image](https://github.com/user-attachments/assets/c54584e4-7eb3-4990-9ecc-c2869f57bbf1)
![image](https://github.com/user-attachments/assets/538fbdc4-b8ad-49e7-808d-9c43c818de8c)
![image](https://github.com/user-attachments/assets/0d0e33b4-b4c5-4d7c-a79b-9858487f6705)
![image](https://github.com/user-attachments/assets/0c53e2ba-80bb-49ea-a9bb-28b196465e3a)
![image](https://github.com/user-attachments/assets/db2bf32a-5791-45f5-a6f6-11dbed861322)
![image](https://github.com/user-attachments/assets/0ea6c8f1-2891-4ad6-a67e-cc1c29207b36)
![image](https://github.com/user-attachments/assets/d059894b-3723-4ced-937d-878a3f151346)
![image](https://github.com/user-attachments/assets/eb606de8-118d-449d-8bf3-6e95f1e67e1b)
![image](https://github.com/user-attachments/assets/a0f51c0d-b11c-4e78-92e6-c008de23f6d9)
![image](https://github.com/user-attachments/assets/1264960c-ca5e-44e5-aaa3-14036b12de8e)
![image](https://github.com/user-attachments/assets/3d10715b-729d-4cb2-8c2d-f4e37fe2b1d8)


1. brute force directory -- > /blog

2. register & try CVE-2022-3552.py, fail

3. brute force directory --> .git

4. git-dumper --> obtain all of the source code

5. bb-config.php --> get user name and password

6. git log --> get email address

7. exploit with CVE-2022-3552.py using the email address and password obtained from git

```bash
Moudle "pwn" not found in Python3 --> external package which Kali prevent to install directly: 
1. python3 -m venv bullybox-venv
2. source bullybox-venv/bin/activate
3. pip install pwntools
4. deactivate 
```
