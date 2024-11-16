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



