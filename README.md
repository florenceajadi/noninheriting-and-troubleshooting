<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Creating Non-Inheriting Organizational Units for GPO Testing and Troubleshooting</h1>
This tutorial outlines the implementation of creating non-inheriting OUs for GPO Testing in Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Create Non-Inheriting OUs for GPOs](https://youtu.be/cG7M3Z-Cek4)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
  
<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create a new GPO
- Link GPO to a domain
- Link an existing GPO to two domain folders
- Add user to GPO delegations and set permission level


<h2>Deployment and Configuration Steps</h2>

<p>
<img src="" height="80%" width="80%""/>


</p>
<p>
Diagram
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/61c2035d-a9d4-4d47-a6cd-9950759f3c24" height="80%" width="80%""/>



</p>
<p>
Created a new OU within CyberGirl OU folder and named it 'Test(Non-inheriting)'.
</p>
<br />

<p>
 <img src="https://github.com/user-attachments/assets/ba30c7c6-5484-4a85-a1b6-1ab4240f8e39" height="80%" width="80%""/>
   <img src="https://github.com/user-attachments/assets/98d0849b-7954-419a-a4f0-5d5a67e93570" height="80%" width="80%""/>
</p>
<p>
Enabled 'Disabled Active Desktop' and going to troubleshoot using command prompt 'gpupdate' to check on updates on policies.
</p>
<p>
  <img src="https://github.com/user-attachments/assets/15efe62a-06dd-4728-8586-4480b936ecd6" height="80%" width="80%""/>
  <img src="https://github.com/user-attachments/assets/2c60d68f-5c39-4df5-9c95-0d5f93f9266f" height="80%" width="80%"" />
</p>
<p> Running 'gpresult /r' on command prompt to see the default doman policy under the user setting</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/e169478f-31e9-4bd2-800c-6ec18bae2cbd" height="80%" width="80%""/>

</p>

<p>
  I am also going to create a GPO in this domain (Test - noninheriting folder) and name it 'Test GPO'.
</p>
<p>
 <img src="https://github.com/user-attachments/assets/090d1bdb-d054-4595-be6c-b4456fbe3c34" height="80%" width="80%""/>
</p>
<p> Created a new folder in C:\TestFolder path within my User Configuration </p>
<p>
  <img src="https://github.com/user-attachments/assets/4e3333ca-361a-413f-93e9-347d00ea76ac" height="80%" width=80%" />
</p>
<p>Used 'gpupdate /force' which shows the computer policy and user policy has been updated and completed. </p>
<p>
  <img src="https://github.com/user-attachments/assets/3b074249-c9e0-4e24-a67b-14922bda9d92" height="80%" width="80%" />
  <img src="https://github.com/user-attachments/assets/86117d15-d360-4eb5-a4b6-bb227bf7313f" height="80%" width=80%" />
</p>
<p>'gpresult /r' can see the Test GPO and the Default Domain Policy</p>
<br />


<p>
<img src="https://github.com/user-attachments/assets/febe3726-fdc8-43aa-afb3-5085f28983b7" height="80%" width="80%""/>
  <img src="https://github.com/user-attachments/assets/251db637-0256-4f0c-af26-03119b59b9df" height="80%" width="80%""/>
</p>

  
<p> Blocked inheritance on Test (Non-Inheriting) and used command prompt to 'gpupdate /force' the update. Also used 'gpresult /r'. If we see the user Settings, Test GPO is the only one available because we disabled the inheritance.
 </p>
