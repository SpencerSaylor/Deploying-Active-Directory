<p align="center">
<img src="https://i.imgur.com/ji8tw98.png" width="50%" height="50%"/>
</p>

<h1>Part 1</h1>
</b>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Install Active Directory</h2>
<p>
  1. Login to DC-1 and install Active Directory Domain Services
  <ol>
    <li>Go to Server Manager</li>
        <img src="https://i.imgur.com/DteXJIp.png"/>
    <li>Hover over "Manage"</li>
     <img src="https://i.imgur.com/g2NS0fl.png"/>
    <li>select "Add roles and features</li>
    <li>Select Role-based installation in and select next</li>
    <img src="https://i.imgur.com/iVBue8j.png"/>
    <li>Use server from the server pool. In this case, it'll be our windows server VM I created and click next.</li>
    <img src="https://i.imgur.com/oam0q8h.png"/>
    <li>In select server roles, select Active Directory Services</li>
    <img src="https://i.imgur.com/yhDISVQ.png"/>
    <li>Select add features then click next</li>
    <img src="https://i.imgur.com/DihNMHI.png"/>
    <li>When you get to Confirmation, select "restart the destination server automatically if required.</li>
    <li>Then selcet Install</li>
  </ol>
</p>

<p>
  2. Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)
</p>
<img src="https://i.imgur.com/7mrHiNB.png"/>

<p>
  3. Restart and then log back into DC-1 as user: mydomain.com\labuser
</p>

<h2>Create a Domain Admin user within the domain</h2>
<p>
  1. In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”
</p>

<p>
  2. Create a new OU named “_ADMINS”
</p>

<p>
  3. Create a new employee named “Jane Doe” (same password) with the username of “jane_admin” / Cyberlab123!
</p>
  
<p>
  4. Add jane_admin to the “Domain Admins” Security Group
</p>
<ol>
  <li>go to _ADMINS folder in ADUC</li>
  <li>Right click Jane Doe and select properties</li>
  <li>Select member of</li>
  <li>Click add</li>
  <li>Type domain admins and click check names</li>
  <img src="https://i.imgur.com/gNqChPl.png"/>
  <li>click "OK"</li>
</ol>

<p>
  5. Log out / close the connection to DC-1 and log back in as “mydomain.com\jane_admin”
User jane_admin as your admin account from now on
</p>

<h2>Join Client-1 to your domain (mydomain.com)</h2>
<p>
  1. Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will restart)
</p>

<p>
  2. Login to the Domain Controller and verify Client-1 shows up in ADUC
Create a new OU named “_CLIENTS” and drag Client-1 into there
</p>

<h1>Part 2</h1>
</b>

<h2>Setup Remote Desktop for non-administrative users on Client-1</h2>
<p>
  1. Log into Client-1 as mydomain.com\jane_admin
</p>

<p>
  2. Open system properties
</p>

<p>
  3. Click “Remote Desktop”
</p>

<p>
  4. Allow “domain users” access to remote desktop
</p>

<p>
  5. You can now log into Client-1 as a normal, non-administrative user now.
Normally you’d want to do this with Group Policy that allows you to change MANY systems at once
</p>

<h2>Create a bunch of additional users and attempt to log into client-1 with one of the users</h2>

<p>
  1. Login to DC-1 as jane_admin
</p>
 
<p>
  2. Open PowerShell_ise as an administrator
</p>

<p>
  3. Create a new File and paste the contents of the script into it
</p>

<p>
  4. Run the script and observe the accounts being created
</p>

<p>
  5. When finished, open ADUC and observe the accounts in the appropriate OU　(_EMPLOYEES)
</p>

<p>
  6. Attempt to log into Client-1 with one of the accounts (take note of the password in the script)
</p>







