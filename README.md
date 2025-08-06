# AWS Public Subnet Firewall Simulation Project 🚀
This project demonstrates practical AWS networking concepts by simulating a firewall using a public subnet, security groups, and network ACLs (NACLs). It shows how to control inbound/outbound traffic at both subnet and instance levels, verifying behavior using real HTTP traffic tests.

## 📌 What This Project Covers
✅ Creating a custom VPC with public subnets
✅ Launching an EC2 instance as a public web server
✅ Configuring Security Groups for instance-level traffic control
✅ Setting up Network ACLs (NACLs) for subnet-level rules
✅ Simulating blocking/allowing ports by editing security group & NACL rules
✅ Testing using browser and CLI tools (curl, nmap)
✅ Documenting behavior for inbound and outbound connections

## 🛠️ Project Steps
1. **VPC and Subnet Setup:**

   * Created a custom VPC with a public subnet.
   * Attached an Internet Gateway for external connectivity.

2. **EC2 Web Server:**

   * Deployed an EC2 instance in the public subnet.
   * Installed a simple HTTP server to serve a web page on port 80.

3. **Security Group Rules:**

   * Initially allowed inbound HTTP (port 80) from anywhere to confirm connectivity.
<img width="1355" height="316" alt="Screenshot 2025-08-06 at 2 23 01 PM" src="https://github.com/user-attachments/assets/2933a3ab-1902-45d2-8574-48738b01a131" />

   * Later removed HTTP inbound permission to simulate blocking access.
<img width="1353" height="301" alt="Screenshot 2025-08-06 at 2 25 16 PM" src="https://github.com/user-attachments/assets/48d597ed-f2a5-4222-a64d-8a880aaab15f" />


4. **NACL Configuration:**

   * Configured NACL rules to explicitly allow or deny traffic to certain ports.
<img width="630" height="387" alt="Screenshot 2025-08-06 at 4 56 41 PM" src="https://github.com/user-attachments/assets/6f179e57-22c5-416f-89a9-7078fb50706f" />

   * Denied inbound HTTP (port 80) in NACL to simulate a subnet-level firewall block.

5. **Testing:**

   * Verified accessibility of the web page from an external browser.
<img width="668" height="900" alt="Screenshot 2025-08-06 at 2 51 01 PM" src="https://github.com/user-attachments/assets/1bf52815-ae0e-4b90-8f45-875fbfc2f9aa" />

   * Observed results after modifying rules (e.g., HTTP denied → webpage inaccessible).
<img width="669" height="900" alt="Screenshot 2025-08-06 at 2 55 48 PM" src="https://github.com/user-attachments/assets/5ae8a990-d09c-4f86-adff-60905c5f3f89" />

   * Confirmed behavior aligns with security group & NACL documentation.

## 🖼️ Architecture Diagram
<img width="1024" height="1024" alt="architecture" src="https://github.com/user-attachments/assets/6ee53d9c-f4f3-4637-8836-0b00e3725cb1" />

## 🧪 Tools Used
* AWS VPC, EC2, Security Groups, NACLs
* curl & nmap for testing
* Browser for HTTP checks

## 📖 Key Learnings
* Security Groups control instance-level traffic; NACLs control subnet-level traffic.
* NACLs are stateless → return traffic needs explicit allow rules.
* Security Groups are stateful → allow responses automatically if request allowed.
* Denying inbound port traffic in NACL blocks ALL sources, including instances within the same subnet.
