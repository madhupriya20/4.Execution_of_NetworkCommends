
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

## Program 
Client
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
~~~
Server 
~~~
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
### netstat
![netstat](https://github.com/user-attachments/assets/f4eefdf5-13ee-42ae-828e-921f6f160b5b)
### ipconfig
![ipconfig](https://github.com/user-attachments/assets/5c89b140-9748-454f-8724-e91a669cacc0)
### arp
![arp](https://github.com/user-attachments/assets/e26358ad-dbe6-4650-bce4-d4b413ddb229)
### getmac
![getmac](https://github.com/user-attachments/assets/e30cd17f-351c-49d2-afad-115ba8d45097)
### hostname
![hostname](https://github.com/user-attachments/assets/72ac9cc1-6bcf-4f99-9eb0-a1340e7c9141)
### netstat
![nbstat](https://github.com/user-attachments/assets/3ed11b03-3af6-4ee2-854f-20778e35b51a)
### nslookup
![nslookup](https://github.com/user-attachments/assets/e381db08-eee6-45ac-9cc7-db5f451ee1fe)
### png
![png](https://github.com/user-attachments/assets/d901a342-baea-4461-9197-d8bddd11d3d7)
### system info 
![system info](https://github.com/user-attachments/assets/4060f4ab-841e-451d-8dfd-99a06f553a90)
### traceert
![tracert](https://github.com/user-attachments/assets/a54d6839-482f-4f13-8cd4-1fb507f950fb)

### Program output 
![Screenshot 2025-05-17 121029](https://github.com/user-attachments/assets/6aaf1d1c-5004-445c-afde-8a82c236f1a8)




## Result
Thus Execution of Network commands Performed 
