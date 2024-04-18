# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

# PROGRAM: 
Find out the ip address of the attackers system.

##  OUTPUT:
![ethical-5 1](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/c4b7240a-120b-4d3a-973d-d2e9e2d0a343)


## OUTPUT:
![ethical-5 2](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/ead81bbc-f02e-488d-9c50-c33cfdb05d71)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![ethical-5 3](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/2da6af00-fcd0-47d6-a37c-2cead4320b12)


Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
## OUTPUT:

![ethical-5 4](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/84b79936-645d-4c6e-8b44-09f25a3c7291)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

# OUTPUT:

![ethical-5 5](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/fbef6b61-319c-44c4-b7d0-c984a3b1f573)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
# OUTPUT:
![ethical-5 6](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/d7004af8-b1de-4c22-bac1-ec47f8d13fe7)


Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![ethical-5 7](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/7bcfc39f-352b-45ff-b5cc-37280bab8b1a)


The info command provides information regarding a module or platform.
# OUTPUT:
![ethical-5 8](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/19bbf463-c0e5-4510-970a-b102fa2dd4c5)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

# MYSQL ENUMERATION:
```
            Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.
```
db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
# OUTPUT:

![ethical-5 9](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/9197b0a9-1c26-4068-a87a-d41b6fa7fad6)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![ethical-5 10](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/5645d624-1ebe-41bf-9c4e-e9ac72616c8d)


use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![ethical-5 11](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/8362367b-46a0-4096-86b6-1f558fd36bcd)

Use the set rhosts command to set the parameter and run the module, as follows:

![ethical-5 12](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/601a153e-0a0c-444e-ac7a-b47dfed54f5d)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![ethical-5 13](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/d4db1ff7-2507-4221-95e4-a6ec29f2471d)


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![ethical-5 14](https://github.com/jagadeeshreddy561/Metasploit-for-reconnaissance/assets/120623104/0ba7bce4-0f57-444d-b0e9-90e16c010f39)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
