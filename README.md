<h5>Directory</h5> 

<b>[Tech Portfolio Home](https://github.com/Jays1115/Jalen-Smith.git)</b>

# Testing Cloud Application for Cloud-Native Traits

<h2>Description</h2>
Scenario: Verizon is developing a new VPN service called Sasha, designed to support both internal employees and external customers with secure connections to the Verizon Cloud Platform. Sasha enables traffic monitoring, analytics, and vulnerability mitigation by filtering incoming traffic and enforcing proper authorization.
<br/><br/>
Newly assigned to this project, I am tasked with verifying the whether Version's new cloud application (Sasha) is implementing cloud native traits: redundancy, resiliency, and least priviledge.
<br>

<h3>Starting the Testing Application</h3>
I initiated a Python program to run tests on Sasha, which is currently running four instances of the Squid VPN proxy servers concurrently. The console output confirms that all four pods are up and running, and the web status shows the service is “Running” and actively serving traffic. This establishes a baseline for our testing: <br/><br/>
<p align="center">
<img src="images/Screenshot 2024-10-23 at 8.54.32 AM.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
<br/>
<br/>


<h2>Redundancy & Resiliency Test:</h2>
<p align="center">
Using the kill command to terminate Squid VPN proxy servers: <br/>
<img src="images/Screenshot 2024-10-23 at 8.58.21 AM.png" height="90%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-10-23 at 8.58.52 AM.png" height="90%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p align="center">
Using the scale command to go from 4 to 5 active servers: <br/>
<img src="images/Screenshot 2024-10-23 at 9.00.20 AM.png" height="90%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p align="center">
Using the scale command to go from 5 to 2 active servers: <br/>
<img src="images/Screenshot 2024-10-23 at 11.36.47 AM.png" height="90%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h3>Findings</h3>
As shown in the test screenshots, the redundancy and resiliency tests were successful. After terminating a Squid VPN proxy server using the kill command, the application remained available to users, demonstrating its redundancy and resiliency. Additionally, Sasha automatically created a new proxy server to replace the one I manually terminated, further highlighting its resiliency.<br/><br/>

Using the scale command effectively demonstrates Sasha's ability to dynamically adjust its capacity based on demand, either scaling up or down as needed. This capability further emphasizes the redundant and resilient design of the system, ensuring that it can handle varying workloads while maintaining availability and performance. By efficiently managing resources, Sasha is able to provide a robust and reliable service that adapts to changing user demands without compromising security or functionality.

<h2>Least Priviledge Test:</h2>
<p align="center">
Using the get-user command to view the default user each server is running as:  <br/>
<img src="images/Screenshot 2024-10-23 at 11.22.07 AM.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>

<h3>Findings</h3>
Sasha did not pass this test, as the results revealed that each server is running under the root user. This presents a significant security risk, as following the principle of least privilege is critical for minimizing potential vulnerabilities. Running processes as root increases the attack surface, making the system more susceptible to exploitation. For a cloud-native service like Sasha, ensuring that each server operates with the minimum necessary permissions is essential to maintaining security and aligning with best practices. <br/><br/>
