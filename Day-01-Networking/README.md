<!-- Animated Header Banner -->
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=90%20Days%20of%20DevOps&fontSize=50&fontColor=fff&animation=twinkling&fontAlignY=35&desc=Week%201%20%7C%20Networking%20Fundamentals&descAlignY=60&descSize=20" width="100%"/>

<!-- Badges -->
[![DevOps](https://img.shields.io/badge/DevOps-90Days%20Challenge-0A66C2?style=for-the-badge&logo=devdotto&logoColor=white)](https://github.com)
[![Week](https://img.shields.io/badge/Week-1%20of%2013-FF6B6B?style=for-the-badge&logo=clockify&logoColor=white)](https://github.com)
[![Focus](https://img.shields.io/badge/Focus-Networking-00C896?style=for-the-badge&logo=cisco&logoColor=white)](https://github.com)
[![2025](https://img.shields.io/badge/Edition-2025-FFD700?style=for-the-badge&logo=calendar&logoColor=black)](https://github.com)

</div>

---

<div align="center">

## 🌐 Welcome to Week 1 — Networking for DevOps

> *"A network is reliable only when every engineer understands the invisible roads that data travels."*

</div>

Welcome to **Week 1** of the **#90DaysOfDevOps – 2025 Edition**! 🚀  
This week we dive deep into **Networking** — the invisible backbone that powers every application, cloud instance, and DevOps pipeline you'll ever build.

---

## 📋 Table of Contents

- [🌍 How Does the Internet Work?](#-how-does-the-internet-work)
- [📡 What is the Internet? Protocols Explained](#-what-is-the-internet-protocols-explained)
- [🧱 OSI Model vs TCP/IP Model](#-osi-model-vs-tcpip-model)
- [🔢 IP Addressing — IPv4, IPv6 & Subnetting](#-ip-addressing--ipv4-ipv6--subnetting)
- [🪪 IP Address vs MAC Address](#-ip-address-vs-mac-address)
- [🔀 Routers vs Switches](#-routers-vs-switches)
- [🛠️ Key Protocols & Ports for DevOps](#️-key-protocols--ports-for-devops)
- [☁️ AWS EC2 & Security Groups](#️-aws-ec2--security-groups)
- [💻 Networking Commands Cheat Sheet](#-networking-commands-cheat-sheet)
- [📌 Week 1 Tasks Summary](#-week-1-tasks-summary)

---

## 🌍 How Does the Internet Work?

<div align="center">

```
  YOU (Browser)
       │
       ▼
  ┌─────────────┐
  │  Your ISP   │  ← Internet Service Provider
  └──────┬──────┘
         │
         ▼
  ┌─────────────────────────────────┐
  │      The Internet Backbone      │
  │  (Fiber cables, Undersea cables,│
  │   Satellite links, Data Centers)│
  └──────────────┬──────────────────┘
                 │
         ┌───────┴────────┐
         ▼                ▼
   ┌───────────┐    ┌───────────┐
   │  DNS      │    │  Server   │
   │ Resolver  │    │ (Website) │
   └───────────┘    └───────────┘
```

</div>

The Internet is essentially a **global network of networks**. Here's how a simple web request works:

| Step | What Happens |
|------|-------------|
| 1️⃣ | You type `https://google.com` in your browser |
| 2️⃣ | Your device asks a **DNS server** to translate that name to an IP address |
| 3️⃣ | DNS responds: `"google.com → 142.250.182.46"` |
| 4️⃣ | Your browser opens a **TCP connection** to that IP |
| 5️⃣ | An **HTTPS request** is sent to Google's server |
| 6️⃣ | Google's server responds with the web page |
| 7️⃣ | Your browser **renders** the HTML/CSS/JS |

> 💡 **DevOps Insight:** Understanding this flow helps you debug broken pipelines, misconfigured DNS, failing health checks, and latency issues in distributed systems.

---

## 📡 What is the Internet? Protocols Explained

The **Internet** is a massive global system of interconnected computer networks that use **standardized communication protocols (TCP/IP)** to link devices worldwide.

### 🔌 What is a Protocol?

A **protocol** is a set of rules that defines how data is formatted, transmitted, and received between devices.

```
Think of it like a language:
  - English speakers can communicate with English speakers.
  - HTTP "speakers" (clients & servers) can communicate via HTTP.
```

### 🔑 Core Protocols Every DevOps Engineer Must Know

| Protocol | Full Name | Port | Use in DevOps |
|----------|-----------|------|---------------|
| **HTTP** | HyperText Transfer Protocol | `80` | Web traffic, REST APIs |
| **HTTPS** | HTTP Secure (SSL/TLS) | `443` | Secure web traffic, CI/CD webhooks |
| **SSH** | Secure Shell | `22` | Remote server access, Git over SSH |
| **FTP** | File Transfer Protocol | `21` | Legacy file transfers |
| **SFTP** | Secure FTP | `22` | Secure file transfers |
| **DNS** | Domain Name System | `53` | Resolving domain names to IPs |
| **SMTP** | Simple Mail Transfer Protocol | `25` / `587` | Email sending (alerting systems) |
| **MySQL** | MySQL Database | `3306` | DB connections |
| **PostgreSQL** | Postgres DB | `5432` | DB connections |
| **Redis** | Redis Cache | `6379` | Caching layer |
| **Kubernetes API** | K8s API Server | `6443` | Cluster management |
| **Docker** | Docker Daemon | `2376` | Container management |

---

## 🧱 OSI Model vs TCP/IP Model

The **OSI (Open Systems Interconnection)** model is a conceptual framework that describes how data travels across a network in **7 layers**. The **TCP/IP model** is the practical implementation used in real-world networking.

<div align="center">

```
 OSI Model (7 Layers)              TCP/IP Model (4 Layers)
┌───────────────────────┐         ┌───────────────────────┐
│  7. Application       │ ◄──────►│  Application          │
├───────────────────────┤         │  (HTTP, SSH, DNS, FTP) │
│  6. Presentation      │         └───────────────────────┘
├───────────────────────┤                    │
│  5. Session           │                    │
├───────────────────────┤         ┌───────────────────────┐
│  4. Transport         │ ◄──────►│  Transport            │
│  (TCP / UDP)          │         │  (TCP, UDP)           │
├───────────────────────┤         └───────────────────────┘
│  3. Network           │ ◄──────►┌───────────────────────┐
│  (IP, Routing)        │         │  Internet             │
├───────────────────────┤         │  (IP, ICMP, ARP)      │
│  2. Data Link         │         └───────────────────────┘
│  (MAC, Switches)      │ ◄──────►┌───────────────────────┐
├───────────────────────┤         │  Network Access       │
│  1. Physical          │         │  (Ethernet, Wi-Fi)    │
│  (Cables, Signals)    │         └───────────────────────┘
└───────────────────────┘
```

</div>

### 🔍 Real-World Examples Per Layer

| Layer | Name | Real-World DevOps Example |
|-------|------|--------------------------|
| **L7** | Application | `curl https://api.example.com/health` — HTTP request from your CI pipeline |
| **L6** | Presentation | SSL/TLS encryption on HTTPS — your certs managed by `certbot` or ACM |
| **L5** | Session | Maintaining a persistent SSH session to your EC2 instance |
| **L4** | Transport | TCP ensures your Kubernetes pod's log stream arrives in order |
| **L3** | Network | IP routing between VPCs in AWS using route tables |
| **L2** | Data Link | MAC address resolution within the same subnet (ARP protocol) |
| **L1** | Physical | Actual fiber optic cables in AWS data centers |

> 💡 **DevOps Tip:** When troubleshooting, think in layers! Start from L1 (is there connectivity?) → up to L7 (is the app responding?). This is called **bottom-up debugging**.

---

## 🔢 IP Addressing — IPv4, IPv6 & Subnetting

### 🔵 IPv4

IPv4 is a **32-bit** address, written as four octets separated by dots.

```
Example:  192.168.1.100
Binary:   11000000.10101000.00000001.01100100
```

| Class | Range | Usage |
|-------|-------|-------|
| **A** | `1.0.0.0 – 126.255.255.255` | Large networks (ISPs) |
| **B** | `128.0.0.0 – 191.255.255.255` | Medium networks |
| **C** | `192.0.0.0 – 223.255.255.255` | Small networks (home/office) |

**Private IP Ranges (RFC 1918):**
```
10.0.0.0    – 10.255.255.255    → Class A Private
172.16.0.0  – 172.31.255.255    → Class B Private  
192.168.0.0 – 192.168.255.255   → Class C Private (your home router!)
```

### 🟢 IPv6

IPv6 is a **128-bit** address, written in hexadecimal, designed to solve IPv4 exhaustion.

```
Example:  2001:0db8:85a3:0000:0000:8a2e:0370:7334
Shortened: 2001:db8:85a3::8a2e:370:7334
```

| Feature | IPv4 | IPv6 |
|---------|------|------|
| Address size | 32-bit | 128-bit |
| Total addresses | ~4.3 Billion | ~340 Undecillion |
| Header size | 20 bytes | 40 bytes |
| NAT required? | Yes | No |
| AWS support? | ✅ | ✅ |

### 🔀 Subnetting

Subnetting divides a network into smaller segments using a **subnet mask** or **CIDR notation**.

```
IP Address:   192.168.1.0/24
              └──────────┘└─┘
              Network part  Prefix (24 bits = 255.255.255.0)

Hosts available: 2^(32-24) - 2 = 254 hosts
```

**Common CIDR Blocks in AWS:**

| CIDR | Subnet Mask | Usable Hosts |
|------|------------|--------------|
| `/8` | `255.0.0.0` | 16,777,214 |
| `/16` | `255.255.0.0` | 65,534 |
| `/24` | `255.255.255.0` | 254 |
| `/28` | `255.255.255.240` | 14 |
| `/32` | `255.255.255.255` | 1 (single host) |

> 💡 **DevOps Tip:** AWS VPCs use CIDR blocks. A `/16` is common for VPCs, with `/24` subnets split across availability zones.

---

## 🪪 IP Address vs MAC Address

| Feature | IP Address | MAC Address |
|---------|-----------|-------------|
| **Stands for** | Internet Protocol | Media Access Control |
| **Layer** | L3 — Network | L2 — Data Link |
| **Assigned by** | Network/DHCP/Admin | Manufacturer (burned-in) |
| **Format** | `192.168.1.5` | `AA:BB:CC:DD:EE:FF` |
| **Scope** | Global or local routing | Local network (LAN) only |
| **Changes?** | Yes (DHCP, VPN, etc.) | Rarely (can be spoofed) |
| **Used for** | Routing between networks | Communication within a subnet |

```
Analogy:
  IP Address  = Your mailing address (can change if you move)
  MAC Address = Your fingerprint (unique, always with you)
```

---

## 🔀 Routers vs Switches

<div align="center">

```
INTERNET
    │
┌───┴────┐
│ ROUTER │  ← Works at Layer 3 (Network)
│        │    Routes traffic between networks
│        │    Has a public IP (WAN) + private IP (LAN)
└───┬────┘
    │
┌───┴────────┐
│  SWITCH    │  ← Works at Layer 2 (Data Link)
│            │    Connects devices within the same network
│            │    Uses MAC addresses
└────────────┘
    │    │    │
   PC1  PC2  Server
```

</div>

| Feature | Router | Switch |
|---------|--------|--------|
| **OSI Layer** | Layer 3 | Layer 2 |
| **Uses** | IP Addresses | MAC Addresses |
| **Function** | Routes between networks | Connects devices in a LAN |
| **AWS Equivalent** | Route Table / NAT Gateway | VPC Subnet / VLAN |
| **Example** | Your home Wi-Fi router | Office network switch |

> 💡 **DevOps Context:** In AWS, **Route Tables** are software-defined routers. When you set `0.0.0.0/0 → igw-xxxxx`, you're telling the router to send all internet-bound traffic through the Internet Gateway.

---

## 🛠️ AWS EC2 & Security Groups

### 🚀 Launching an EC2 Instance (Step-by-Step)

```bash
# Step 1: Log in to AWS Console → Navigate to EC2

# Step 2: Click "Launch Instance"
Name: my-devops-week1-server
AMI: Ubuntu 22.04 LTS (Free Tier Eligible)
Instance Type: t2.micro (Free Tier)

# Step 3: Key Pair (for SSH access)
→ Create new key pair → Download .pem file
→ chmod 400 my-key.pem  (on Linux/Mac)

# Step 4: Configure Security Group (see below)

# Step 5: Launch!
```

### 🔒 Security Groups — Your Cloud Firewall

Security Groups act as **virtual firewalls** for your EC2 instances, controlling inbound and outbound traffic.

**Example Security Group for a Web Server:**

| Type | Protocol | Port | Source | Purpose |
|------|----------|------|--------|---------|
| SSH | TCP | `22` | `Your IP/32` | Admin access |
| HTTP | TCP | `80` | `0.0.0.0/0` | Public web traffic |
| HTTPS | TCP | `443` | `0.0.0.0/0` | Secure web traffic |
| Custom TCP | TCP | `8080` | `10.0.0.0/16` | Internal app port |
| All traffic | All | All | Same SG | Intra-cluster traffic |

```bash
# Connect to your EC2 after launch:
ssh -i "my-key.pem" ubuntu@<your-ec2-public-ip>

# Verify your instance networking:
ip addr show
curl ifconfig.me   # See your public IP
```

> ⚠️ **Security Best Practice:** Never open port `22` to `0.0.0.0/0` in production. Always restrict SSH to your specific IP.

---

## 💻 Networking Commands Cheat Sheet

### 🏓 `ping` — Test Connectivity

```bash
ping google.com              # Ping by domain
ping 8.8.8.8                 # Ping by IP (Google DNS)
ping -c 4 google.com         # Send only 4 packets
ping -i 0.5 google.com       # Ping every 0.5 seconds

# Output to understand:
# 64 bytes from 142.250.182.46: icmp_seq=1 ttl=118 time=12.3 ms
#                                                         └── Latency!
```

> 📌 **Use case:** Check if your EC2 instance can reach the internet or if a downstream service is reachable.

---

### 🔍 `traceroute` / `tracert` — Trace Packet Route

```bash
traceroute google.com        # Linux/Mac
tracert google.com           # Windows

# Each line = one "hop" (router)
# 1  192.168.1.1    1.2ms    ← Your local router
# 2  10.0.0.1       3.4ms    ← ISP gateway
# ...
# 10 142.250.x.x    12.3ms   ← Google's server
```

> 📌 **Use case:** Diagnose where packets are being dropped in your network path to an AWS service.

---

### 📊 `netstat` — Network Statistics

```bash
netstat -tuln               # Show all listening ports
netstat -an                 # All connections with addresses
netstat -p                  # Show which process owns each connection
ss -tuln                    # Modern replacement for netstat

# Example output:
# tcp  0  0  0.0.0.0:22   0.0.0.0:*   LISTEN  → SSH is listening!
# tcp  0  0  0.0.0.0:80   0.0.0.0:*   LISTEN  → HTTP server running
```

> 📌 **Use case:** Verify which ports your application is listening on. Essential for debugging "connection refused" errors.

---

### 🌐 `curl` — Make HTTP Requests

```bash
curl https://api.github.com              # Basic GET request
curl -I https://google.com               # Fetch only headers
curl -X POST https://api.example.com/data \
     -H "Content-Type: application/json" \
     -d '{"key": "value"}'              # POST with JSON body

curl -o file.txt https://example.com/file  # Download file
curl -L https://short.url/abc            # Follow redirects
curl -v https://google.com               # Verbose (debug SSL/TLS)

# Check your EC2's public IP:
curl ifconfig.me
curl ipinfo.io/json
```

> 📌 **Use case:** Test REST APIs, health check endpoints, download packages in scripts, debug SSL certificates.

---

### 🔎 `dig` / `nslookup` — DNS Lookup

```bash
# dig (recommended)
dig google.com                  # Basic DNS lookup
dig google.com MX               # Mail server records
dig google.com NS               # Name server records
dig google.com TXT              # TXT records (SPF, DKIM)
dig @8.8.8.8 google.com         # Query using Google's DNS
dig +short google.com           # Clean output

# nslookup (classic)
nslookup google.com             # Resolve domain → IP
nslookup 8.8.8.8               # Reverse lookup (IP → domain)
nslookup -type=MX google.com    # Find mail servers
```

> 📌 **Use case:** Debug DNS propagation issues after deploying on AWS Route 53, verify your domain is pointing to the right IP.

---

### 🗂️ Quick Command Reference Card

```
╔══════════════════════════════════════════════════════════════╗
║          🛠️  DEVOPS NETWORKING COMMANDS QUICK REF           ║
╠══════════════╦═══════════════════════════════════════════════╣
║ ping         ║ Test basic connectivity & latency             ║
║ traceroute   ║ Map the route packets take to a destination   ║
║ netstat/ss   ║ View open ports & active connections          ║
║ curl         ║ Make HTTP requests, test APIs, download files ║
║ dig/nslookup ║ Query DNS records & resolve hostnames         ║
║ ifconfig/ip  ║ View/configure network interfaces             ║
║ nmap         ║ Scan ports on a remote host (ethically!)      ║
║ tcpdump      ║ Capture and analyze raw network traffic       ║
║ iptables     ║ Linux firewall rules (like Security Groups)   ║
║ wget         ║ Download files from the web                   ║
╚══════════════╩═══════════════════════════════════════════════╝
```

---

## 📌 Week 1 Tasks Summary

| # | Task | Status |
|---|------|--------|
| 1 | ✅ Understand OSI & TCP/IP Models with real-world examples | Done |
| 2 | ✅ Study protocols & ports relevant to DevOps workflows | Done |
| 3 | ✅ Launch AWS EC2 + configure Security Groups | Done |
| 4 | ✅ Practice networking commands — create cheat sheet | Done |

---

## 🔗 Resources & References

- 📘 [AWS VPC Documentation](https://docs.aws.amazon.com/vpc/)
- 📘 [Cloudflare: How Does the Internet Work?](https://www.cloudflare.com/learning/network-layer/how-does-the-internet-work/)
- 📘 [Subnetting Practice](https://subnettingpractice.com/)
- 📘 [OSI Model Deep Dive — Cisco](https://www.cisco.com/c/en/us/solutions/enterprise-networks/what-is-computer-networking.html)
- 📘 [90DaysOfDevOps GitHub](https://github.com/MichaelCade/90DaysOfDevOps)

---

## 🙌 Connect With Me

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com)
[![Twitter](https://img.shields.io/badge/Twitter-Follow-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com)

**#90DaysOfDevOps** • **#DevOps** • **#Networking** • **#AWS** • **#Linux** • **#CloudComputing**

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer&animation=twinkling" width="100%"/>

*⭐ If this helped you, star the repo and share it with your DevOps community!*

</div>
