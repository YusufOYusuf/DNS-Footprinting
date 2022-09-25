<h1>DNS Footprinting</h1>


<h2>Description</h2>
In this lab I learned nslookup and dig which are two commonly used DNS footprinting tools. 
<br />



<h2>Environments Used </h2>

- <b>Kali GNU/Linux</b> 
- <b>openSUSE</b>

<h2>Program walk-through:</h2>

<p align="center">
Open and review nslookup’s manual by typing the "man nslookup" command.: <br/>
<img src="https://i.postimg.cc/R0yxmZQV/Screen-Shot-2022-09-25-at-3-43-11-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
<br />
Once finished reviewing the man page, press the Q character to quit and bring the shell prompt back.:  <br/>
<img src="https://i.postimg.cc/NjvWpnGL/Screen-Shot-2022-09-25-at-3-46-54-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
<br />
In the Terminal window, initiate nslookup interactive mode by typing the "nslookup" command, then press Enter. Then At the prompt, we can type "server" to see our current lookup server: <br/>
<img src="https://i.postimg.cc/YCzL9jdR/Screen-Shot-2022-09-25-at-3-49-43-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  

  
  
  
<br />
For this lab environment, the DNS server we want to query is only listening on IP address 192.168.0.254. Change the default server by typing the following
command and pressing Enter.:  <br/>
<img src="https://i.postimg.cc/VNY3nHmM/Screen-Shot-2022-09-25-at-3-54-34-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
 
 
 
 
 
 
 <br />
In the lab environment, we have a domain called mylab.com, and we want to see what the root domain resolves to. To do a domain lookup, type the "mylab.com" command and press Enter:  <br/>
<img src="https://i.postimg.cc/sgqJRTgS/Screen-Shot-2022-09-25-at-3-58-14-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
 
 
 
 
 
 
 
  
<br />
Type in the command "set type=ns". the command "set" allows you to explore the different dns record types. after this type in "mylab,com" :  <br/>
<img src="https://i.postimg.cc/fLkmPXxy/Screen-Shot-2022-09-25-at-4-03-32-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
  
  
  
  
  
<br />
By default, nslookup returns a records. Here we will look up the a record for the
host opensuse.mylab.com by typing the command "set type=a" then "opensuse.mylab.com":  <br/>
<img src="https://i.postimg.cc/d36kxq5s/Screen-Shot-2022-09-25-at-4-12-24-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
  
  
  
  
  
  
  
 <br />
Now try to return mx (mail servers) records for the domain. You will notice that it will not respond:  <br/>
<img src="https://i.postimg.cc/wvfYfZhK/Screen-Shot-2022-09-25-at-4-15-24-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
   
  
  
  
  
  
  
 <br />
One lookup type not on the list is any. Instinctively, you may want to set the type
to any and get everything back! Newer DNS servers do not return everything for
the zone. While getting some good information, you will not see all the hosts or
a records on that domain. Try the "any" command:  <br/>
<img src="https://i.postimg.cc/WzvY77yR/Screen-Shot-2022-09-25-at-4-18-24-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
  
  
  
  
  
  
  
  
  
  <br />
In order to get to see EVERYTHING, you need to be able to access an axfr
(transfer) record. Normally, these are not available. You can test this on the Kali
machine by typing the "set type=axfr" then typying "mylab.com:  <br/>
<img src="https://i.postimg.cc/qqFhTmHS/Screen-Shot-2022-09-25-at-4-21-10-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
  
  
  
  
  
  
<br />
Manuever to the openSUSE OS and go to the terminal window and type "nslookup" then after that type command "set type=axfr" and then "mylab.com". In the output you will see every record on the domain, including A, SOA, CNAME, TXT, MX, and NS records. When done type exit to leave.:  <br/>
<img src="https://i.postimg.cc/hvng7Tbv/Screen-Shot-2022-09-25-at-4-26-48-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
  
  
  
  
  

<br />
Dig is a similar tool used for viewing DNS information. Type the
command "dig @192.168.0.254 mylab.com ns" into the OpenSUSE terminal to see the nslookup equivalent of a
nameserver lookup and press Enter:  <br/>
<img src="https://i.postimg.cc/fbbvDrGT/Screen-Shot-2022-09-25-at-4-32-45-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 


























  
  
  
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
