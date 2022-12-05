# Day 5 Brute Forcing - He knows when you're awake

## Use Hydra to find the VNC password of the target with IP address 10.10.192.241. What is the password?

I am using [Threader 3000](https://github.com/dievus/threader3000) to scan all ports of the machine. 

![image](https://user-images.githubusercontent.com/34974437/205657870-3f888093-fb56-41d2-bafe-39631546f160.png)

From running the above nmap scan, we discover there is a vnc service running on port 5900.  
As stated by the hint, the VNC server does not use a username. We can use Hydra to bruteforce the login using the rockyou wordlist
![image](https://user-images.githubusercontent.com/34974437/205657777-6863b352-65fc-4855-9eab-a28e23a9e2fb.png)  
We have now successfully brute forced the password for vnc and can attempt to login.

## Using a VNC client on the AttackBox, connect to the target of IP address 10.10.192.241. What is the flag written on the target’s screen?

We can use the remote desktop client Remmina to connect to the target machine. 

I launched Remmina by simply typing 'remmina' in the terminal. Clicking cancel on the keyring popup brought me straight to the main page of Remmina.  
Here I was able to input our target ip and change the connection to VNC.

Next we simply enter the password we brute forced earlier, and we are in :)


![image](https://user-images.githubusercontent.com/34974437/205659061-1c9ecec5-2951-48bc-8865-637f7c904298.png)  

You will be able to retrieve the flag from the bottom right of the target machine's desktop

![image](https://user-images.githubusercontent.com/34974437/205660116-5c44efc2-8b19-47b7-9f0b-ceb54d440559.png)
