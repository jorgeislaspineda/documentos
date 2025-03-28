**Prepare jenkins installation for Ubuntu**
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```
**Linux Ubuntu update**
```
sudo apt-get update
```
**Jenkins intallation**
```
sudo apt-get install jenkins
```
**Start Jenkins**

**Enable jenkins service:**
```
sudo systemctl enable jenkins
```
**Start Jenkins service:**
```
sudo systemctl start jenkins
```

**Check jenkins status:**
```
sudo systemctl status jenkins
```
**Output after status jenkins**

jenkins.service - Jenkins Continuous Integration Server
     Loaded: loaded (/usr/lib/systemd/system/jenkins.service; enabled; preset: enabled)
     Active: active (running) since Fri 2025-03-21 20:30:45 UTC; 13s ago
   Main PID: 7496 (java)
      Tasks: 45 (limit: 4023)
     Memory: 400.2M (peak: 405.8M)
        CPU: 17.803s
     CGroup: /system.slice/jenkins.service
             └─7496 /usr/bin/java -Djava.awt.headless=true -jar /usr/share/java/jenkins.war --webroot=/var/cache/jenkins/war --httpPort=8080

Mar 21 20:30:37 LnxVM098203 jenkins[7496]: 3e76d501c6c34d7ba08775d3042c2e97
Mar 21 20:30:37 LnxVM098203 jenkins[7496]: **This may also be found at: /var/lib/jenkins/secrets/initialAdminPassword**[^1].
Mar 21 20:30:37 LnxVM098203 jenkins[7496]: *************************************************************
Mar 21 20:30:37 LnxVM098203 jenkins[7496]: *************************************************************
Mar 21 20:30:37 LnxVM098203 jenkins[7496]: *************************************************************
Mar 21 20:30:45 LnxVM098203 jenkins[7496]: 2025-03-21 20:30:45.491+0000 [id=30]        INFO        jenkins.InitReactorRunner$1#onAttained: Completed ini>
Mar 21 20:30:45 LnxVM098203 jenkins[7496]: 2025-03-21 20:30:45.520+0000 [id=23]        INFO        hudson.lifecycle.Lifecycle#onReady: Jenkins is fully >
Mar 21 20:30:45 LnxVM098203 systemd[1]: Started jenkins.service - Jenkins Continuous Integration Server.
Mar 21 20:30:46 LnxVM098203 jenkins[7496]: 2025-03-21 20:30:46.001+0000 [id=46]        INFO        h.m.DownloadService$Downloadable#load: Obtained the u>
Mar 21 20:30:46 LnxVM098203 jenkins[7496]: 2025-03-21 20:30:46.002+0000 [id=46]        INFO        hudson.util.Retrier#start: Performed the action check>
~

**Password**
```
jislas@LnxServer1:~$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
3e76d501c6c34d7ba08775d3042c2e97
```
<img width="996" alt="Image" src="https://github.com/user-attachments/assets/ee044ae9-e279-46fc-951b-ce4d4658e9c3" />
<img width="993" alt="Image" src="https://github.com/user-attachments/assets/94fae293-e32c-4c90-b0b4-8b84d2355754" />
<img width="987" alt="Image" src="https://github.com/user-attachments/assets/ab5d49ff-df29-4704-919b-1a2dbf6c0ac8" />
<img width="991" alt="Image" src="https://github.com/user-attachments/assets/e8346e5c-db1b-4965-af71-eb214ce0d243" />
<img width="993" alt="Image" src="https://github.com/user-attachments/assets/33bc5f7b-eae6-4b2f-a0bf-7a0382e5d0ae" />
<img width="1435" alt="Image" src="https://github.com/user-attachments/assets/1ce89e67-00e5-4f65-8d7b-f700c8ce8d4a" />
<img width="1433" alt="Image" src="https://github.com/user-attachments/assets/ac223686-0f35-46d9-9307-d68c4621eaa8" />
<img width="1433" alt="Image" src="https://github.com/user-attachments/assets/f78fe7a5-f5ff-43d4-8e3b-2078f163c578" />

>[!NOTE]
>Visit the oficial jenkins site for more details.

>[!IMPORTANT]
>https://www.jenkins.io/doc/book/installing/linux/#debianubuntu.

[^1]: Password
