🌐 Day 1 – Networking Basics for DevOps | #90DaysOfDevOps 🚀

📅 Week 1 Focus: Networking
👨‍💻 Author: Rameshwar Mane
🎯 Goal: Build strong networking fundamentals for DevOps

📌 Topics Covered
🌍 How Internet Works
🔗 Protocols & Ports
🧱 OSI Model vs TCP/IP Model
🌐 IP Address (IPv4 & IPv6 + Subnet)
🔑 IP vs MAC Address
🔀 Routers & Switches
💻 Networking Commands
☁️ AWS EC2 & Security Groups
🌍 1. How Does the Internet Work?

The internet is a global network of interconnected computers.

🔄 Flow:
User enters URL (e.g., google.com)
DNS converts domain → IP address
Request travels through routers
Server processes request
Response sent back to client

💡 Example:
Browser = Client
Server = Backend
Internet = Communication medium

🔗 2. Protocols & Ports

Protocols are rules that define communication between systems.

🔥 Common Protocols:
Protocol	Port	Usage
HTTP	80	Web traffic
HTTPS	443	Secure web
FTP	21	File transfer
SSH	22	Remote login
DNS	53	Domain resolution

💡 DevOps Use Case:

Deploy app → HTTP/HTTPS
Connect server → SSH
🧱 3. OSI vs TCP/IP Model
🔹 OSI Model (7 Layers)
Physical
Data Link
Network
Transport
Session
Presentation
Application

💡 Example:

Application → HTTP
Transport → TCP
Network → IP
🔹 TCP/IP Model (4 Layers)
Network Access
Internet
Transport
Application
⚡ Key Differences
OSI Model	TCP/IP Model
7 Layers	4 Layers
Theoretical	Practical
Learning model	Real-world usage
🌐 4. IP Addressing
🔹 IPv4
Format: 192.168.1.1
32-bit
Limited addresses
🔹 IPv6
Format: 2001:0db8:85a3::8a2e:0370:7334
128-bit
Future-ready
🔹 Subnetting

Used to divide networks into smaller parts:

Improves performance
Enhances security
🔑 5. IP Address vs MAC Address
IP Address	MAC Address
Logical	Physical
Changeable	Fixed
Assigned by network	Assigned by manufacturer

💡 Analogy:

IP = Current address
MAC = Permanent identity
🔀 6. Routers & Switches
Router	Switch
Connects networks	Connects devices
Uses IP address	Uses MAC address
Layer 3 device	Layer 2 device
💻 7. Networking Commands Cheat Sheet
# Check connectivity
ping google.com

# Trace route
tracert google.com   # Windows
traceroute google.com  # Linux/Mac

# Network stats
netstat -an

# HTTP request
curl https://example.com

# DNS lookup
nslookup google.com
dig google.com
☁️ 8. AWS EC2 & Security Groups
EC2 = Virtual machine in cloud
Security Group = Firewall
🔐 Example Rules:
Allow port 22 → SSH
Allow port 80 → HTTP
Allow port 443 → HTTPS
🎯 Conclusion

Networking is the backbone of DevOps.

Understanding:

IP addressing
Protocols
OSI Model
Routing

👉 Gives you a strong foundation for cloud & DevOps 🚀

📢 My #90DaysOfDevOps Journey

This is Day 1 – Networking Basics

🔜 Coming Next:

AWS EC2 Hands-on
Security Groups Deep Dive
Docker Basics
⭐ Support

If you found this helpful:

⭐ Star this repo
🔁 Share with others
🤝 Connect with me
🔗 Connect With Me
GitHub: (Add your link)
LinkedIn: (Add your link)
📌 Tags

#DevOps #Networking #90DaysOfDevOps #AWS #BeginnerFriendly