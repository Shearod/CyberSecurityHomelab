<h1>Cybersecurity Mini Home Lab</h1>

 ### 

<h2>Description</h2>
Project consists of creating a mini virtual hacking envirornment. This is a safe environment and nothing that we do will affect your host machine. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>YAML</b>
- <b>Docker</b>
- <b>Docker Compose</b>

<h2>Environments Used </h2>

- <b>Windows 11</b>
- <b>OWASP Juice Shop</b>
- <b>DVWA</b>

<h2>🛠️ Setup:</h2>

<p align="center">
Install Docker Desktop: <br/>
  
* **Windows:** Download for free from [docker.com](https://www.docker.com). Run the installer and be sure **Use WSL 2 backend** is checked. Restart if prompted.

  <p align="center">

 Verify Docker Is Running: <br/>

  Open your terminal (PowerShell) and enter:
```powershell
 docker --version
 ```
 <img src="https://imgur.com/LodFU42.png" height="80%" width="80%" alt="Home Lab"/>
<br />
<br />
Create a folder named cyber-lab on your desktop and move into it: <br/>

```powershell
cd $HOME\Desktop\cyber-lab
 ```
<br />
<br />

Open Notepad on your device and paste the following content:

```yaml
services:
  juice-shop:
    image: bkimminich/juice-shop
    ports:
      - "3000:3000"

  dvwa:
    image: vulnerables/web-dvwa
    ports:
      - "8080:80"
```

<img src="https://i.imgur.com/BCp6xHk.png" height="80%" width="80%" alt="Home Lab"/>
<br />
<br />


While Docker is running in the background, enter the following command in your terminal:

```powershell
docker compose up
```
<br />
<br />

🎯 Target Apps
Once the startup process completes, open your web browser and visit these sites:

* OWASP Juice Shop: http://localhost:3000

* DVWA (Damn Vulnerable Web Application): http://localhost:8080

<br />
<br />

 😎Hands-On Vulnerability Exercises
Exercise 1: SQL Injection (DVWA)
Go to http://localhost:8080.

1. Log in with the default credentials:

Username: ```text``` admin

Password: ```text password```

2. Click Create / Reset Database on the setup page, then log back in using the same credentials.

3. Go to DVWA Security in the left menu, set the security level to Low, and click submit.

4. Select SQL Injection from the left menu.

5.To see standard behavior, type ```text 1``` into the User ID box and submit.

6. Now, break out of the query by typing the following payload into the box and submitting:

```sql 1' OR '1'='1```

<img src="https://i.imgur.com/9zScK00.png" height="80%" width="80%" alt="Home Lab"/>
<br />

Result: The app will return EVERY user in the app. You have just performed a SQL Injection! 🙌

<br />

Exercise 2: Cross-Site Scripting / XSS (DVWA)
1. Select XSS (Reflected) from the DVWA menu.

2. In the name input box, inject the following JavaScript code:
   ```html <script>alert('hacked')</script> ```
3. Submit

   <img src="https://i.imgur.com/Svm8e2f.png" height="80%" width="80%" alt="Home Lab"/>


Result: A browser pop-up window will appear displaying the word 'hacked'. You have successfully made the page execute injected frontend code.

<br />
<br />

Exercise 3: Bypassing Authentication (Juice Shop)

1. Navigate to http://localhost:3000

2. Go to Account -> Login.

3. In the email field, inject the following SQL payload:

   ```SQL ' OR 1=1-- ```
4. Type whatever you want in the password field and press SUBMIT

Result: You will automatically be logged in as the platform's site administrator without knowing their actual password.

<br />

🧼Clean Slate
Stuck and want a clean slate? Press Ctrl + C in your running terminal window to stop the lab, then execute ```powershell docker compose up``` again.

Finish for the day?

```powershell docker compose down```



