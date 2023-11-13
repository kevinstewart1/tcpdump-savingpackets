# Saving Packet Captures

# Description
 - In this lab I will demonstrate how to access and manage group policies using the Group Policy Management Tool. This application allows you to set policies that will manage the way machines in your domain behave. You can apply these policies to the whole domain or to separate Organizational Units (OUs). In this instance, I want to add a new policy regarding the Desktop Wallpaper, to the Developers OU that I created in the virtual domain.
   
# Enviornments & Utilities Used
 - Tcpdump
 - Linux Virtual Machine

# Walkthrough
<p align="center">
Saving Captured Packets:
 <br/>
 In the terminal I will use the command: "sudo tcpdump -i eth0 port 80 -w http.pcap &"
 <img src="https://i.imgur.com/QlCmP7L.png" height="60%" width="60%"<br/>
 <br/>
 <br/>
 To list all running jobs, use the following command: "jobs -l"
  <img src="https://i.imgur.com/YxEerdO.png" height="60%" width="60%"<br/>
<br/>
<br/>
Now, I will execute the following command: "curl example.com" to generate some traffic. This command fetches the html from "example.com" and prints it on the screen. 
 <br/>
<img src="https://i.imgur.com/JFA7cNj.png" height="60%" width="60%"<br/>
<br/>
<br/>
Once that's done, use the job ID to bring the process to foreground with the following command: fg % 725 <br/>
<img src="https://i.imgur.com/IGVVZLN.png" height="60%" width="60%"<br/>
<br/>
<br/>
Using CTRL+C will stop the process and it should return a summary of the number of packets captured. Using the command "sudo tcpdump -i eth0 port 80 -w http.pcap" will generate a binary file containing the packets we just captured, called http.pcap.
 <br/>
<img src="https://i.imgur.com/RaiYTpy.png" height="60%" width="60%"<br/>
<br/>
<br/>
We can read from this file using tcpdump now, using this command: "tcpdump -r http.pcap -nv"
<img src="https://i.imgur.com/BDDcJof.png" height="60%" width="60%"<br/>
<br/>
<br/>
 Reading that file we can see there's information about the packets created when I pulled down the html from example.com. Tcpdump writes full packets to the file, not just the text-based analysis that it prints to the screen. For example, in the output you can see the html that was returned as the body of the original query in the terminal.
 <img src="https://i.imgur.com/rNnnnEJ.png" height="60%" width="60%"<br/>
