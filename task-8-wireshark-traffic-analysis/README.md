Task 8: Network Traffic Analysis with Wireshark

Oasis Infobyte Cybersecurity Internship

Name: Letlhogonolo Molokwane  
Task: Capture and Analyse Network Traffic with Wireshark  
Operating system: Windows 11  
Wireshark version: 4.6.7  
Capture target: 127.0.0.1:8000

Introduction

For this task, I used Wireshark to capture and analyse network traffic. I created a small Python web server on my computer and opened its webpage through my browser.

I captured the communication between the browser and the server, filtered the HTTP traffic and examined the TCP connection, HTTP requests and HTTP responses.

Ethical statement

I only captured traffic from the loopback interface on my own computer. The target was "127.0.0.1", which is the localhost address.

I used the capture filter "tcp port 8000", so Wireshark only recorded traffic connected to my test server. I did not capture traffic from another person, external website or unauthorised network.

Demonstration video

I recorded a short demonstration showing the packet capture, HTTP filters, request and response analysis, and TCP three-way handshake.

Watch my Task 8 Wireshark demonstration: https://drive.google.com/file/d/1U82KI4U_Q9ocAWuIs8W5p3-8i9j-LCjH/view?usp=sharing


Tools used

- Wireshark 4.6.7
- Npcap
- Windows 11
- Windows PowerShell
- Python 3.11.9
- Google Chrome
- A local HTML test page

Project files

I organised the evidence into the following folders:

- The `capture` folder contains the saved "wireshark_capture.pcap" file.
- The `screenshots` folder contains evidence of the installation, capture, filters and packet analysis.
- The `test-server` folder contains the harmless HTML page used to generate HTTP traffic.
- This README explains the process and what I found.

What I did

I first installed Wireshark and confirmed that the Npcap loopback capture interface was available.

I created a basic HTML page and started a Python HTTP server on port 8000. I then selected the loopback interface in Wireshark and used the following capture filter:

tcp port 8000


After starting the capture, I opened `http://127.0.0.1:8000` in my browser and refreshed the page three times. I stopped the capture after the browser and server completed their communication.

The final capture contained 36 packets, with no dropped packets.

Starting the local server

I started the test server with:

python -m http.server 8000 --bind 127.0.0.1 --directory ".\test-server"

The local page was available at:

http://127.0.0.1:8000


Capture and display filters

Capture filter

tcp port 8000

I applied this filter before starting the capture. It limited the capture to TCP packets using port 8000.

HTTP display filter

http

This displayed all HTTP requests and responses in the capture.

HTTP request filter

http.request

This displayed only the requests sent by the browser.

HTTP response filter


http.response


This displayed only the responses returned by the Python server.

A capture filter controls which packets are recorded. A display filter does not remove packets from the capture; it only controls which saved packets are visible.

Capture summary

| Item | Result |
|---|---|
| Capture interface | Adapter for loopback traffic capture |
| Source and destination | "127.0.0.1" |
| Server port | TCP port 8000 |
| Total packets captured | 36 |
| Dropped packets | 0 |
| HTTP requests | 3 |
| HTTP responses | 3 |
| Request method | GET |
| Response status | 304 Not Modified |
| Server | SimpleHTTP/0.6 Python/3.11.9 |
| Capture format | PCAP |

TCP three-way handshake

Packets 26, 27 and 28 show an example of a TCP three-way handshake:

| Packet | Direction | Flag | Meaning |
|---:|---|---|---|
| 26 | Client port 39286 to server port 8000 | SYN | The client requests a connection |
| 27 | Server port 8000 to client port 39286 | SYN, ACK | The server accepts and acknowledges the request |
| 28 | Client port 39286 to server port 8000 | ACK | The client confirms the connection |

The three-way handshake establishes a TCP connection before application data is exchanged.

HTTP request analysis

I used the "http.request" filter and selected packet 29.

The packet contained:

GET / HTTP/1.1

The important fields were:

| Field | Captured value | Explanation |
|---|---|---|
| Source address | "127.0.0.1" | The browser was running on my computer |
| Destination address | "127.0.0.1" | The server was also running on my computer |
| Source port | 39412 | Temporary client port selected by Windows |
| Destination port | 8000 | Port used by the Python server |
| Request method | GET | The browser requested a resource |
| Request URI | "/" | The browser requested the main page |
| HTTP version | HTTP/1.1 | Version used by the browser request |
| Host | "127.0.0.1:8000" | Address and port of the test server |
| Connection | keep-alive | The browser requested that the connection remain available |

The complete request URI was:


http://127.0.0.1:8000/

The request also contained a User-Agent header. This gave the server information about the browser and operating-system environment.

HTTP response analysis

I used the "http.response" filter and selected packet 31.

The response contained:


HTTP/1.0 304 Not Modified

The important fields were:

| Field | Captured value | Explanation |
|---|---|---|
| Source address | `127.0.0.1` | The response came from the local server |
| Destination address | `127.0.0.1` | The response was sent back to the browser |
| Source port | 8000 | Port used by the Python server |
| Destination port | 39412 | Temporary client port used by the browser |
| HTTP version | HTTP/1.0 | Version used by the Python server response |
| Status code | 304 | The requested page had not changed |
| Response phrase | Not Modified | The browser could use its cached copy |
| Server | SimpleHTTP/0.6 Python/3.11.9 | Software that generated the response |

Wireshark linked response packet 31 to request packet 29. It reported that the response arrived approximately 7.26 milliseconds after the request.

A "304 Not Modified" response is not an error. The browser included information about its cached copy of the page, and the server confirmed that the page had not changed.

TCP connection closure

The capture also contained FIN and ACK packets. These packets were used to close TCP connections after the browser and server had completed their communication.

This showed the main stages of a network connection:

1. Establish the TCP connection.
2. Send the HTTP request.
3. Return the HTTP response.
4. Close the TCP connection.

Security observations

HTTP traffic is not encrypted. Wireshark was able to display the request method, requested path, host, server software and other headers.

This demonstrates why sensitive websites should use HTTPS. HTTPS encrypts the application data while it travels between the browser and server. An observer may still see some network information, but the HTTP content is protected.

The Server header also revealed the Python version used by the local server. Version information can help administrators during troubleshooting, but it may also give an attacker information about the technology being used. Production servers should avoid exposing unnecessary technical details.

Recommendations

Based on this analysis, I would recommend:

1. Use HTTPS for websites that handle private information.
2. Keep web servers and browsers updated.
3. Avoid sending passwords or personal information through plain HTTP.
4. Limit unnecessary information in HTTP response headers.
5. Monitor network traffic for unusual communication.
6. Use capture filters to avoid collecting unrelated information.
7. Protect saved packet captures because they may contain sensitive data.
8. Only capture network traffic with proper permission.
9. Use firewalls to restrict access to services.
10. Stop local development servers when they are no longer needed.

Limitations

This was a small controlled capture using a local HTTP server. Both the browser and server used the same `127.0.0.1` address.

The capture did not include traffic from an external network, HTTPS decryption, DNS communication or other users. It was created only to demonstrate basic TCP and HTTP analysis safely.

Evidence

The packet capture is saved as:


capture/wireshark_capture.pcap


The screenshots show:

- Wireshark version 4.6.7
- The loopback capture interface
- The complete packet capture
- Filtered HTTP traffic
- HTTP request details
- HTTP response details
- The TCP three-way handshake

Conclusion

This task helped me understand how a browser and web server communicate. I captured the TCP connection, HTTP GET requests, HTTP responses and connection-closing packets.

Wireshark made it possible to inspect each protocol layer and identify the addresses, ports, TCP flags and HTTP fields. The task also demonstrated that normal HTTP traffic is readable during packet analysis, which is why HTTPS is important when sensitive information is transmitted.

All traffic was generated and captured locally on my own computer.

References

- Wireshark User's Guide: https://www.wireshark.org/docs/wsug_html/
- Wireshark Display Filters: https://wiki.wireshark.org/DisplayFilters
- Wireshark Capture Filters: https://wiki.wireshark.org/CaptureFilters