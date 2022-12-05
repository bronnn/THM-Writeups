# GoldenEye TryHackMe Writeup


### Use nmap to scan the network for all ports. How many ports are open?
I am using [Threader 3000](https://github.com/dievus/threader3000) to scan all ports of the machine. 

![image](https://user-images.githubusercontent.com/34974437/205653375-2faffe14-8b24-4ff9-8aaf-b9964b740e8a.png)


### Who needs to make sure they update their default password?
Taking a look at the source code for the web page, there is a comment in the JavaScript file that contains a message.
We discover the user who needs to update their default password. There is also a comment from the developer that informs us of the users encoded password.
Further research uncovers that this method of encoding is HTML encoding. We can do a quick google search for an online tool that will decode this for us. 

![image](https://user-images.githubusercontent.com/34974437/205654358-21e7d325-bdf2-4950-ad30-e441908063b3.png)

With these decoded credentials, we can navigate to /sev-home and login.

Once we login, we see the mention of the pop3 service. The credentials for the website do not seem to work, so we can attempt to use hydra to brute force our login to this service.
![image](https://user-images.githubusercontent.com/34974437/205656435-8dc178aa-6f9b-49d1-97f8-8faa84c6668b.png)



