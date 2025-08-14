# Nmap-scanning-project
Aimed at identifying network devices, uncovering open ports, and checking for vulnerabilities.

### Step 1: 
To scan our devices(host) for open ports, we need to first identify its ip address.

**Procedure**
* Start NMAP from the CMD terminal or open Zenmap.
* Type "ipconfig". This will display all Ip addresses; and select the interface you are using, in this case, the wireless interface.
  
<img width="755" height="752" alt="image" src="https://github.com/user-attachments/assets/18ee4674-d310-4880-a2e0-7975a15625cb" />

### Step 2: Finding network range
To find the network range of all the IP addresses currently connected in the same network(subnet). Type nmap -sn 172.20.10.0/24. Since the host ip is 172.20.10.5, then the network is 172.20.10.0/24
<img width="684" height="537" alt="image" src="https://github.com/user-attachments/assets/db3a915c-6609-4831-a26a-a25df88b77d6" />

---

### Step 3: Scan for open ports
This step involves identifying open ports on the host machine that can lead to an attack or security breach.

**Procedure**
* Select any of the ip addresses in the network.
* Use the nmap command to identify open ports(nmap 172.20.10.5<host ip address>)
  <img width="689" height="330" alt="image" src="https://github.com/user-attachments/assets/063fd117-d94e-4c2c-a24e-cbac1ea51792" />

  ---
### Step 4: Identify Services
This step involves identifying the services being used by the host machine (target).

**Procedure**
* Select any of the ip addresses in the network.
* Use the nmap command to identify services (nmap -sV 172.20.10.5<target ip address>)
  <img width="689" height="414" alt="image" src="https://github.com/user-attachments/assets/d19d9233-86d1-484b-a49d-7118cbefcae8" />

  ---
  ### Step 5: Discovering service version vulnerabilities
  We selected one of the identified services and searched for the version's vulnerabilities:    Microsoft Windows netbios-ssn
  Below are the results of the vulnerabilities discovered:
  <img width="1199" height="543" alt="image" src="https://github.com/user-attachments/assets/765d4b27-7635-467f-aea5-4868f3ea9a35" />

  ### Mitigation reccomendations
  Disable NetBIOS over TCP/IP where it's not needed—e.g., in network adapter settings or via the registry or DHCP options.
  Block NetBIOS-related firewall ports like 137, 138, and 139 at network edges to reduce exposure.
  Ensure all relevant Windows updates and patches are applied, especially the ones referencing MS00‑047, MS08‑034, MS16‑077, etc.




