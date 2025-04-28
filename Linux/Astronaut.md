![image](https://github.com/user-attachments/assets/1f45447f-0585-47f9-85aa-917f85cb778a)
![image](https://github.com/user-attachments/assets/d89d19bc-be65-4acc-9f3b-889a8e8aa2c2)
![image](https://github.com/user-attachments/assets/202fe48b-002a-418a-9b4f-61f9e55ecc11)
![image](https://github.com/user-attachments/assets/b22f94f3-f4c6-44a0-8298-3e4b7e69dfc7)
![image](https://github.com/user-attachments/assets/50d176ef-0fcc-4a8f-a41d-11a19c87200a)
![image](https://github.com/user-attachments/assets/bd749837-d62f-45dc-ab50-e43ffde19dc1)
![image](https://github.com/user-attachments/assets/57d6b472-ed3f-4843-8b8c-4a10b93de8cb)
![image](https://github.com/user-attachments/assets/1d6c9553-8ca1-4972-bded-a2a74149a946)
![image](https://github.com/user-attachments/assets/68888827-865b-4cd2-b707-70b68e788dfe)


1. nmap --> port 80, grav-admin

2. directory brute-force --> grav-admin/admin, login, etc.

3. Exploit-DB 49973.py --> reverse shell www-data

4. /etc/passwd --> user alex      www-data cannot ls or read

5. linpeas --> /usr/bin/php7.4   (SUID)

6. GTFOBins php --> www-data eduid=root --> get proof.txt

7. if check Cron Jobs (cd /var/www/html/grav-admin;/usr/bin/php bin/grav scheduler 1>> /dev/null 2>&1) --> point to /usr/bin/php7.4

![image](https://github.com/user-attachments/assets/2a1f7466-a8ae-4972-a5a0-4f8e9724e1cd)
