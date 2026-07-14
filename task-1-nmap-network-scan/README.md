**Task 1: Basic Network Scanning with Nmap**



**Oasis Infobyte Cybersecurity Internship**



**Name:** Letlhogonolo Molokwane  

**Task:** Basic Network Scanning with Nmap  

**Operating system:** Windows  

**Target scanned:** 127.0.0.1  

**Nmap version:** 7.99



**Introduction**



For this task, I used Nmap to scan my own computer and check which TCP ports were open. I also created a small local web server so that I could see how Nmap detects a running service.



I only scanned "127.0.0.1". This is the localhost address of my computer, so I did not scan another person's computer, a public website or an unauthorised network.



**Tools I used**



\- Nmap 7.99

\- Windows PowerShell

\- Python 3.11.9

\- A Python HTTP server

\- Google Chrome

\- Windows Snipping Tool



**Project files**



**I organised my work into three folders:**



\- The "demo-server" folder contains the "index.html" page that I used to start the local web server.

\- The "results" folder contains the original Nmap scan output in "nmap\_scan\_results.txt".

\- The "screenshots" folder contains screenshots showing the installation, commands, scan results and port 8000 test.

\- The main "README.md" file explains what I did and what I found.



**What I did**



I first installed Nmap and checked that it was working. After that, I performed a basic scan of my computer using the localhost address.



I then created a simple HTML page and started a Python web server on port 8000. While the server was running, I scanned port 8000 and Nmap showed that it was open. I used service detection to find out what type of service was running on the port.



For the final scan, I scanned TCP ports 1 to 10000 and saved the results in a text file. I stopped the Python server when I finished and scanned port 8000 again. This time, Nmap showed that the port was closed.



**Commands I used**



**I checked the installed Nmap version with:**



powershell:

nmap --version





**I performed the first scan with:**



powershell:

nmap 127.0.0.1





**I started the local Python web server with:**



powershell:

py -m http.server 8000 --bind 127.0.0.1 --directory ".\\demo-server"





**I checked whether port 8000 was open with:**



powershell:

nmap -sT -p 8000 127.0.0.1





**I used the following command to identify the service:**



powershell:

nmap -sT -sV -p 8000 127.0.0.1





**I performed and saved the final scan with:**



powershell:

nmap -sT -sV -p 1-10000 127.0.0.1 -oN ".\\results\\nmap\_scan\_results.txt"





**After stopping the Python server, I checked port 8000 again with:**



powershell:

nmap -sT -p 8000 127.0.0.1





**My scan results**



The final scan took about 84 seconds. Nmap scanned 10000 TCP ports. It reported that 9991 ports were closed, eight were open and one was filtered.



**These were my results:**





|**Port**|**State**|**Service reported by Nmap** |**What I found**|
|-|-|-|-|
|135|Open|Microsoft RPC|This is used by Windows services to communicate with each other.|
|137|Filtered|NetBIOS Name Service|Nmap could not fully check this port because its probes appeared to be filtered.|
|445|Open|Microsoft-DS|This port is normally connected to Windows file and printer sharing.|
|1434|Open|Microsoft SQL Server 2022|Nmap detected the SQL Server installation on my computer.|
|2015|Open|HTTP|Nmap detected a Go-based HTTP service, but I could not confirm the exact application from this scan alone.|
|5040|Open|Unknown|Nmap found an open port but could not identify the service using it.|
|5354|Open|mDNS responder|This type of service is normally used to discover devices and services on a local network.|
|7680|Open|Delivery-related service|On Windows, this port is commonly associated with Windows Delivery Optimization.|
|8000|Open|Python HTTP server|This was the temporary web server that I started for the task.|







**Port 8000 test**



Port 8000 was the main port I used for my demonstration. While my Python server was running, Nmap reported:





8000/tcp open http SimpleHTTPServer 0.6 (Python 3.11.9)





I then stopped the server by pressing "Ctrl + C". When I scanned the port again, Nmap reported that it was closed.



This helped me understand that an open port normally means that a program is running and listening for network connections. When I stopped the program, the port changed back to a closed state.



**What the port states mean**



**Open**



An application is running and accepting connections through the port.



**Closed**



The computer responded to the scan, but no application was listening on that port.



**Filtered**



Nmap could not confirm whether the port was open or closed. This can happen when a firewall or another security control blocks the scan.



**Security meaning of the results**



I learned that an open port does not automatically mean that the computer has a vulnerability. It means that a service is listening on that port.



Open ports still need to be checked because every running network service can increase the attack surface of a computer. Services that are not needed should be stopped. Services that are needed should be updated and protected with suitable firewall rules and authentication.



The scan was performed against "127.0.0.1", so the results only show what I could access locally from my computer. The scan does not prove that all these ports can be accessed by other computers or through the internet.



**Recommendations**



**Based on the results, I would recommend the following:**



1\. Stop services that are not being used.

2\. Investigate services that are running on unknown ports.

3\. Keep Windows, Python and SQL Server updated.

4\. Restrict access to the SQL Server database.

5\. Do not expose Windows file-sharing port 445 to untrusted networks.

6\. Use Windows Defender Firewall to control incoming connections.

7\. Use strong passwords and authentication for important services.

8\. Keep development servers on "127.0.0.1" when outside access is not needed.

9\. Perform authorised Nmap scans regularly to notice unexpected changes.

10\. Confirm scan findings manually because Nmap may not always identify a service correctly.



**Limitations**



This was a basic local scan. I only scanned TCP ports 1 to 10000, and I did not scan UDP ports. I also did not attempt to exploit any service.



Nmap identifies services by analysing their responses. This means some of the service names can be estimates instead of confirmed results.



**Evidence**



**The original scan output is saved in:**





results/nmap\_scan\_results.txt





The screenshots folder contains evidence of the Nmap installation, local webpage, scan commands, detected services and the port 8000 open-and-closed test.



**Conclusion**



I successfully used Nmap to scan my local Windows computer and identify open ports and services. The scan found several Windows services, my Microsoft SQL Server installation and the temporary Python server that I created.



The clearest part of the task was the port 8000 test. Nmap showed the port as open while the Python server was running and closed after I stopped it. This helped me understand how Nmap can be used to check which network services are active on a computer.



**References**



\- Nmap Installation Guide: https://nmap.org/book/install.html

\- Nmap Port Scanning Techniques: https://nmap.org/book/man-port-scanning-techniques.html

\- Nmap Service and Version Detection: https://nmap.org/book/man-version-detection.html

