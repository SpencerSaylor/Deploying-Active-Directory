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
</p>

<p>
  2. Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)
</p>

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

<p>
  5. Log out / close the connection to DC-1 and log back in as “mydomain.com\jane_admin”
User jane_admin as your admin account from now on
</p>
