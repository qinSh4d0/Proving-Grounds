![image](https://github.com/user-attachments/assets/eb23c205-b210-4906-8436-090bd6e53a26)
![image](https://github.com/user-attachments/assets/43801967-4ad5-4866-b2cb-287ed28684c7)
![image](https://github.com/user-attachments/assets/907675e5-f6bf-49ee-9a21-40454744b9f2)
![image](https://github.com/user-attachments/assets/23256caf-9623-4643-8b1d-0aa0c95ccbb7)
![image](https://github.com/user-attachments/assets/d41098f7-adc2-4f63-b980-cfb81dea4520)
![image](https://github.com/user-attachments/assets/b9b105ea-b054-4333-896e-387577b845e4)
![image](https://github.com/user-attachments/assets/7abf3e62-dfd7-462a-8aac-7a8384ddb3ad)

![image](https://github.com/user-attachments/assets/fe1d0f90-5a8a-482b-aebd-9e854d193a78)
![image](https://github.com/user-attachments/assets/1c905167-9783-43c0-aa45-1e6bd6bf3a58)
![image](https://github.com/user-attachments/assets/c1bc538f-49a4-4aac-8bd1-66db05d35e44)
![image](https://github.com/user-attachments/assets/a5d915d1-81ad-4caf-8779-b6a6f67aa921)
![image](https://github.com/user-attachments/assets/8d565070-4e21-418d-9320-457338e6d9c8)
![image](https://github.com/user-attachments/assets/b314342a-3701-4b0e-ad2f-a1f244c14368)
![image](https://github.com/user-attachments/assets/8a7b4d63-73fb-4c34-b026-47c63aeb1491)
![image](https://github.com/user-attachments/assets/005fb110-f172-4734-9504-b8efbad43f63)
![image](https://github.com/user-attachments/assets/e7076990-0454-45d9-ae3a-eb9d49d32e5d)
![image](https://github.com/user-attachments/assets/f48aa5d1-da72-4d13-a5d3-134ff074407c)
![image](https://github.com/user-attachments/assets/9b9ef380-363d-4122-ba36-43b9a2d98a6b)
![image](https://github.com/user-attachments/assets/30549748-f47b-479c-bfe9-0fcace448bb6)

1. Exhibitor Web RCE  --- Exploit-DB 48654

2. sudo -l ---> (ALL) NOPASSWD: /usr/bin/gcore

(gcore is a utility which is used to generate core dumps of running processes. Such files often contain sensitive information.)

3. ps aux ---> list all running processes.

4. PID 513 ---> /usr/bin/password-store   LOOKS INTERESTING

5. sudo gcore -o output 513 ----> dump & save in output

6. strings output.513  ---> get root password

7. su - root --> get proof.txt
