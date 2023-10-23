<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1 align = "center">Installing and Configuring Active Directory in Microsoft Azure</h1>
This lab demonstrates how to install and configure Active Directory using Azure. We will be using two VMs on Azure that are on the same virtual network. One VM will be installed with Active Directory and configured to be the <b>Domain Controller</b> and other VM will be used as a <b>client</b>. Then, we will configure the Active Directory to allow the Client to join the domain as well as creating user accounts using a Powershell script. 

<br />

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Active Directory Domain Services</li>
  <li>Powershell</li>
  <li>(OPTIONAL) Notepad for writing down usernames and passwords for VMs</li>
</ul>

<br />

<h2>Operating Systems Used</h2>
<ul>
  <li>Windows Server 2022</li>
  <li>Windows 10 Pro (21H2)</li>
</ul>

<br />

<h2>Installation Steps</h2>

<h3>Setting up Resources in Azure</h3>

<p>
  <ul>
    <li>Our Client VM should be installed normally using the Windows 10 image (OS)</li>
    <ul>
      <li>Tutorial on how to install VMs and to access them using Remote Desktop can be found <b><a href ="https://github.com/ColtonTrauCC/vm-network">here</a></b></li>
    </ul>      
    <li>Our Domain Controller VM using Active Directory should be created using the image <b>Windows Server 2022 Datacenter: Azure Edition - x64 Gen2</b></li>
    <ul>
      <li><img src = "https://github.com/ColtonTrauCC/active-directory/assets/147654000/2ba43657-9799-46d3-9140-c9952282614e" height="80%" width="80%"/></li>
    </ul>
    <li>After the VMs are created, we'll set the Domain Controller's IP Address as <i>static</i> since having it dynamic will make them difficult for the VM to communicate with our client VM.</li>
    <li>Go to your Virtual Machines in Azure and go to <b>Networking</b> then go to the link listed next to <b>Network Interface</b>. Head to <b>IP Configurations</b> under <b>settings</b>, go to the ipconfig link to open up a window to toggle the IP configuration and allocation to <b>Static</b>.</li>
    <ul>
      <li>IP Configuration for the Domain VM</li>
      <li><img src="https://github.com/ColtonTrauCC/active-directory/assets/147654000/f9883539-f1b2-4ada-80d9-2e0df6c2de6d" height="80%" width="80%"/></li>
    </ul>
  </ul>
</p>

<br />

<h3>Ensuring Connectivity</h3>

<p>
  <ul>
    <li>Logging in to the Client VM, open the Command Prompt and enter the command <b>ping [Domain Controller Private IP Address] -t</b> to endlessly send ping in order ensure reachability with the Domain Controller. Connection should time out after the first ping due to the Domain Controller's Firewall Settings.</li>
    <ul>
      <li><img src = "https://github.com/ColtonTrauCC/active-directory/assets/147654000/be2faa69-d835-4222-a105-b6f5201c018f" height = 80% width = 80% /></li>
    </ul>
    <li>Logging into the Domain Controller VM, go to the <b>Windows Defender Firewall with Advanced Security</b>. Head to the <b>Inbound Rules</b> and enable the rules under the protocol <b>ICMPv4</b>, specifically <i>Core Networking Diagnostics - ICMP Echo Request (ICMPv4-In)</i></li>
    <ul>
	<li><img src = "https://github.com/ColtonTrauCC/active-directory/assets/147654000/63bef2fe-62b6-4230-aac2-d6528f038bc5" height = 80% width = 80% /></li>
    </ul>
    <li>Head back to the Client VM, and we should now be seeing replies</li>
    <ul>
	<li><img src = "https://github.com/ColtonTrauCC/active-directory/assets/147654000/0918e56e-4fe8-497e-aa05-e9e4b3139042" height = 80% width = 80% /></li>
    </ul>
  </ul>
</p>

<br />

<h3>Installing Active Directory on the Domain Controller</h3>

<p>
  <ul>
	  <li>In your Domain Controller VM, go to the Server Manager Dashboard and click on <b>Add Roles and Features</b>. Go through the installation process and upon getting to <b>Server Roles</b>, make sure to check the box for <b>Active Directory Domain Services</b></li>
	  <ul>
	    <li><img src = "https://github.com/ColtonTrauCC/active-directory/assets/147654000/0b835d58-c357-40ce-a759-a0770c7929c9" height = 80% width = 80% /></li>
	  </ul>
	 <li>Once installed, we now have to promote the server into a domain controller. To do so, you may notice a <b>warning notification</b> on the top right where the flag icon is. Click on that flag and click <b>Promote this server to a domain controller</b>. Click on Add a new forest and specify a domain name. For this tutorial, we'll name the domain <b>mydomain.com</b>, specifiy the password, and proceed with the install. Noted, you will be automatically signed out, re-log in through Remote Desktop, and installation is fully completed!</li>
	  <ul>
	    <li><img src = "https://github.com/ColtonTrauCC/active-directory/assets/147654000/af0fb9e9-2f55-4fb0-a372-487d2dab317e" height = 80% width = 80% /></li>
	    <li><img src = "https://github.com/ColtonTrauCC/active-directory/assets/147654000/fb6b02e1-2e22-4147-aede-1d126c634ec8" height = 80% width = 80% /></li>
    	 </ul>
  </ul>
</p>

<br />

<h2>Configuration Steps</h2>

<h3></h3>

<p>
  <ul>
    <li></li>
  </ul>
</p>

<br />
