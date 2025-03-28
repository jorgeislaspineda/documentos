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
![alt text](https://github.com/jorgeislaspineda/documentos/main/1.png?raw=true)

>[!NOTE]
>Visit the oficial jenkins site for more details.

>[!IMPORTANT]
>https://www.jenkins.io/doc/book/installing/linux/#debianubuntu.

[^1]: Password
