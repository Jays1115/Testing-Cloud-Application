<h5>Directory</h5> 

<b>[Tech Portfolio Home](https://github.com/Jays1115/Jalen-Smith.git)</b>

# Testing-Cloud-Application

<h2>Description</h2>
Scenario: Version is developing a new VPN service called Sasha. Sasha will support both Verizon internal employees and external customers for their
secured connection to the Verizon Cloud Platform. It allows for traffic monitoring, analytics, and vulnerability mitigation by filtering incoming traffic and requires proper
authorization.
<br/><br/>
Newly assigned to this project, I am tasked with verifying the whether Version's new cloud application (Sasha) is implementing cloud native traits: redundancy, resiliency, and least priviledge.
<br>

<h3>Starting the Testing Application</h3>
Starting a python program to run tests on Sasha. Currently Sasha is running four copies of the squid VPN proxy servers concurrently. The console output shows that all four pods are up and running and the web status output also indicates the service is “Running” and serving traffic. This establishes the baseline for our testing: <br/><br/>
<p align="center">
<img src="images/Screenshot 2024-10-23 at 8.54.32 AM.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
<br/>
<br/>


<h2>Redundancy & Resiliency Test:</h2>
<p align="center">
Killing procxy servers to see if they come back: <br/>
<img src="images/Screenshot 2024-10-23 at 8.58.21 AM.png" height="90%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-10-23 at 8.58.52 AM.png" height="90%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
Testing the scalling feature of the cloud application: <br/>
<img src="images/Screenshot 2024-10-23 at 9.00.20 AM.png" height="90%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h3>Findings</h3>
Starting a python program to run tests on Sasha. Currently Sasha is running four copies of the squid VPN proxy servers concurrently. The console output shows that all four pods are up and running and the web status output also indicates the service is “Running” and serving traffic. This establishes the baseline for our testing: <br/><br/>

<h2>Least Priviledge Test:</h2>
Selecting the correct S3 bucket associated with the beach website (website-bucket-cfc90080):  <br/>
<img src="images/Screenshot 2024-10-23 at 11.22.07 AM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<h3>Findings</h3>
Starting a python program to run tests on Sasha. Currently Sasha is running four copies of the squid VPN proxy servers concurrently. The console output shows that all four pods are up and running and the web status output also indicates the service is “Running” and serving traffic. This establishes the baseline for our testing: <br/><br/>
