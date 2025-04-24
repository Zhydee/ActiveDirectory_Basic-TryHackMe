<h2>🧠 TryHackMe – Active Directory Basics</h2>

<p>This repository contains my personal notes and summaries from the <strong>"Active Directory Basics"</strong> room on TryHackMe. The room provides hands-on experience with essential AD concepts used in real-world enterprise environments.</p>

<h3>🔍 Topics I Covered:</h3>
<ul>
  <li><strong>Organizational Units (OUs):</strong> Understanding how to structure and organize users, groups, and computers within Active Directory.</li>
  <li><strong>User Management:</strong> Creating, deleting, and managing users, including using <strong>delegation</strong> to grant specific administrative privileges without giving full control.</li>
  <li><strong>Device Management:</strong> Adding and managing computer objects inside the domain, and understanding how AD tracks and authenticates devices.</li>
  <li><strong>Group Policy Objects (GPO):</strong> Implementing and applying GPOs to control system configurations and enforce security settings across the domain.</li>
</ul>

<p>This lab helped reinforce foundational knowledge for roles like SOC analyst, system administrator, and blue team operations.</p>

<h2>Program walk-through:</h2>

<p align="center">
Launch the software: <br/>
<img src="https://i.imgur.com/0EcKvoE.png" height="80%" width="80%" alt="Active Directory Users and Computers"/>
<br />
<br />
<h2>Create New Organizational Unit:</h2>
  <p>For this part, I will create a mockup OU named Students under THM.</p>
<p align="center">
Right click OU called THM:  <br/>
<img src="https://i.imgur.com/q7TjNDi.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Enter the name: <br/>
<img src="https://i.imgur.com/Sy5dVxe.png" height="80%" width="50%" alt="AD"/>
<br />
<br />
Result:  <br/>
<img src="https://i.imgur.com/H8eOdeF.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
  
<h2>Managing Users in Active Directory:</h2>
<h3>Deleting OU:</h3>
<p>For this part, I will delete OU called Research and Development since the department has been closed in the scenario.</p>
<p align="center">
Enable advanced features:  <br/>
<img src="https://i.imgur.com/ZE8cALN.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Right click OU and go to properties. Under Object tab, untick "Protect object from accidental deletion":  <br/>
<img src="https://i.imgur.com/uVVyNdt.png" height="80%" width="50%" alt="AD"/>
<br />
<br />
Right Click OU, choose delete and click yes:  <br/>
<img src="https://i.imgur.com/VqYxb6f.png" height="80%" width="50%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>
<h3>Grant User Specific Privileges (Delegate Control):</h3>
<p>For this part, I will grant a specific privilege to Phillip since he is the leader of his department.</p>
<p align="center">
Right click OU & choose delegate control:  <br/>
<img src="https://i.imgur.com/HbzvvsC.png" height="80%" width="50%" alt="AD"/>
<br />
<br />
Enter user name, and click check names:  <br/>
<img src="https://i.imgur.com/h8SFci6.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Confirmed presence of the user in OU & click OK:  <br/>
<img src="https://i.imgur.com/h8SFci6.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Choose task to delegate:  <br/>
<img src="https://i.imgur.com/ho5Sn0w.png" height="80%" width="50%" alt="AD"/>
<br />
<p>Now, Phillip should be able to reset passwords for any user in the sales department</p>

<h2>Organizing Devices:</h2>
<p align="center">
  <p>For this part, all laptop and pc will be move to OU called workstation while all server move to OU called servers. This is because having all of devices in one OU is not the best idea since it's very likely that we want different policies for our servers and the machines that regular users use on a daily basis.</p>
  <p align="center">
At the start, all devices in OU called Computers:  <br/>
<img src="https://i.imgur.com/FXB84rS.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Create OU called Workstations: <br/>
<img src="https://i.imgur.com/0n0HK1q.png" height="80%" width="50%" alt="AD"/>
<br />
<br />
Create OU called Servers: <br/>
<img src="https://i.imgur.com/qQZyK6Q.png" height="80%" width="50%" alt="AD"/>
<br />
<br />
Result for Workstations:  <br/>
<img src="https://i.imgur.com/4njabnf.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Result for Servers:  <br/>
<img src="https://i.imgur.com/IzjhiHd.png" height="80%" width="80%" alt="AD"/>
<br />

<h2>Group Policies:</h2>
<h3>Edit Group Policy:</h3>
<p align="center">
  <p>For this part, I will modified existing group policy called Default Domain Policy</p>
  <p align="center">
Launch group policy management:  <br/>
<img src="https://i.imgur.com/hLX784y.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Click on the group policy and go to Setting tab:  <br/>
<img src="https://i.imgur.com/q7WX3t6.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Right click the GPO & choose edit:  <br/>
<img src="https://i.imgur.com/ErWUFxy.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
In this scenario, I will change the highlighted policy value:  <br/>
<img src="https://i.imgur.com/RrZmyZk.png" height="80%" width="80%" alt="AD"/>
<br />
<br />
Change the policy value from 7 to 10:  <br/>
<img src="https://i.imgur.com/PY49l7T.png" height="80%" width="50%" alt="AD"/>
<br />
<br />
Result:  <br/>
<img src="https://i.imgur.com/7q8hcM3.png" height="80%" width="80%" alt="AD"/>
<br />
<h3>Create New Group Policy:</h3>
<p>For this part, I will create new policy called Restrict Control Panel Access.</p>
<p align="center">
Create new GPO & named it Restrict Control Panel Access:  <br/>
<img src="https://i.imgur.com/3hyzg68.png" height="80%" width="50%" alt="AD"/>
<br />
