
## NAME:MADHUPRIYA R
## REGNO:212224040177
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>
## PROGRAM
CLIENT
~~~
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    ip = input("Enter the website you want to ping (or type 'exit' to quit): ")
    s.send(ip.encode('utf-8'))
    if ip.lower() == 'exit':
        break
    print(s.recv(4096).decode('utf-8'))

s.close()

SERVER
import socket
from pythonping import ping

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server listening on port 8000...")
c, addr = s.accept()
print(f"Connection from {addr}")

while True:
    try:
        hostname = c.recv(1024).decode('utf-8')
        if not hostname or hostname.lower() == 'exit':
            print("Client disconnected.")
            break
        response = ping(hostname, verbose=False, count=4)
        c.send(str(response).encode('utf-8'))
    except Exception as e:
        c.send(f"Ping failed: {e}".encode('utf-8'))

c.close()
~~~

## Output
netstat
![image](https://github.com/user-attachments/assets/322cf1ac-9f6b-47b6-aec5-f87ca7689814)


ipconfig


<img width="960" alt="2025-05-19 (1)" src="https://github.com/user-attachments/assets/c921e247-e52d-4387-8934-1e3a25e620b4" />


arp


<img width="960" alt="2025-05-19 (2)" src="https://github.com/user-attachments/assets/3e2303d6-da7e-4c57-8987-f3d8cd79cedd" />


getmac


<img width="960" alt="2025-05-19 (3)" src="https://github.com/user-attachments/assets/7ea4eae1-fcc2-41d1-bbec-ffd4b6b1a7e3" />


hostname

<img width="960" alt="2025-05-19 (4)" src="https://github.com/user-attachments/assets/9a11d044-2984-46e0-b945-0ad83d784786" />


nbtstat
<img width="960" alt="2025-05-19 (5)" src="https://github.com/user-attachments/assets/f4933a3f-3c74-492c-87c1-ccea5bac1eab" />


nslookup


![444752845-e381db08-eee6-45ac-9cc7-db5f451ee1fe](https://github.com/user-attachments/assets/46cfb1fc-4453-44c1-a4f3-a21c6bd5950d)

png

![444752855-d901a342-baea-4461-9197-d8bddd11d3d7](https://github.com/user-attachments/assets/7db2e19c-0d93-4a59-a95c-efc287bd8209)



systeminfo


![444752897-4060f4ab-841e-451d-8dfd-99a06f553a90](https://github.com/user-attachments/assets/74eaa302-dd46-4724-836d-6c8466ea5a68)



tracert


![444752973-a54d6839-482f-4f13-8cd4-1fb507f950fb](https://github.com/user-attachments/assets/c02bfcf6-cd67-4ac7-80b5-16f2fafefd8d)



Program output
![444753481-6aaf1d1c-5004-445c-afde-8a82c236f1a8](https://github.com/user-attachments/assets/ddff1524-c524-4278-9830-b8c0d67ef263)


## Result
Thus Execution of Network commands Performed 
