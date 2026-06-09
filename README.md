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


While Docker is running in the background, enter the following command in your terminal:

```powershell
docker compose up
```
<br />
<br />




