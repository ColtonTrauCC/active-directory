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

<h3>Setting up Resources in Azure/h3>

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
    <li>After the VMs are created, we'll set their IP Addresses as <i>static</i> since having them dynamically will make them difficult for the VMs to communicate with each other.</li>
    <li>Go to your Virtual Machines in Azure and go to <b>Networking</b> then go to the link listed next to <b>Network Interface</b>. Head to <b>IP Configurations</b> under <b>settings</b>, go to the ipconfig link to open up a window to toggle the IP configuration and allocation to <b>Static</b>.</li>
    <ul>
      <li>IP Configuration for the Domain VM</li>
      <li><img src="https://github.com/ColtonTrauCC/active-directory/assets/147654000/f9883539-f1b2-4ada-80d9-2e0df6c2de6d" height="50%" width="50%"/></li>
    </ul>
  </ul>
</p>

<br />

<br />

<h2>Configuration Steps</h2>

<h3></h3>

<p>
  <ul>
    <li></li>
  </ul>
</p>

<br />
