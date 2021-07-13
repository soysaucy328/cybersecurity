## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is:

**_Searched using the following: site:demo.testfire.net "CEO"_**

- How can this information be helpful to an attacker:

**_This information can be used to social engineer an attack._**


#### Step 2: DNS and Domain Discovery

**went on and put in the domain demo.testfire.net https://centralops.net/co/DomainDossier.aspx**

Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

  1. Where is the company located: 

  **_Sunnyvale, CA_**

  2. What is the NetRange IP address:

  **_65.61.137.64/26_**

  3. What is the company they use to store their infrastructure:

  **_Rackspace Backbone Engineering (C05762718)_**

  4. What is the IP address of the DNS server:

  **_65.61.137.117_**
  
#### Step 3: Shodan

- What open ports and running services did Shodan find:

#### Step 4: Recon-ng

- Install the Recon module `xssed`. 
- Set the source to `demo.testfire.net`. 
- Run the module. 

Is Altoro Mutual vulnerable to XSS: **_Yes it is, this was determined after running the recon/domains-vulnerabilites/xssed module_**

![recon-ng](16-Penetration-Testing/Homework/images/recon-ng.jpg)

### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine: 

**_nmap -sV 192.168.0.10_**

![nmap](16-Penetration-Testing/Homework/images/nmap.jpg)
 
- Bonus command to output results into a new text file named `zenmapscan.txt`:

**_nmap -sV -oN zenmapscan.txt**

- Zenmap vulnerability script command: 

**_nmap -sV -oN zenmapscan.txt --script smb-enum-shares 192.168.0.10_**

![nmap2](16-Penetration-Testing/Homework/images/nmap2.jpg)

- Once you have identified this vulnerability, answer the following questions for your client:
  1. What is the vulnerability:

  2. Why is it dangerous:

  3. What mitigation strategies can you recommendations for the client to protect their server:

---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.  

