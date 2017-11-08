Open Source Project:  Pi-hole
-----------------------------

Authors:  
<ul>            
<li>Michael Galde </li>
<li>Carmel Waka </li>
<li>Olivier Avande</li>
<li>Srikanth Vadla</li>
</ul>
Team Name: R3tr0

Our group "R3tr0" focused on the software security aspect for the open source project Pi-hole and have developed the following five assurance claims


Assurance Claims
-----------------
<ul>
    <li><b>Claim 1: The Pi-Hole user interface has no exploitable HTTP weakness. </b></br>The Pi-hole makes use of lighhtpd software package due to its minimal framework and the ease of which the system can be configured.
</li>
<li><b>Claim 2: Pi-Hole attack surface is minimized. </b></br>The attack surface of the Pi-hole software is minimized by utilizing best practices approaches to software development and community involvement.
</li>
<li><b>Claim 3: The Pi-Hole minimizes the possibility of device compromised during patching. </b></br>Patching is done in safe and secure environment requiring administrator privileges to minimize any related risks to updates.
</li>
<li><b>Claim 4: The Pi-Hole authentication mechanism is acceptably secure against the threat of unauthorized access. </b></br>Pi-Hole authentication mechanism implemented enough authentication practices and it is safe enough from the high-level threat which is "unauthorized access".
</li>
<li><b>Claim 5: The Pi-Hole DNS server is adequately safe from denial of service attacks. </b></br>The Pi-hole system uses dnsmasq as the underlying dns server to provide ad filtering. It is lightweight and requires minimal resources.
Like all dns services, it is exposed to denial of service. However, using the appropriate configuration it can be adequately secured.
</li>
</ul>

Security Requirements
---------------------
The development of assurance cases for each assurance claim allowed us to develop misuse cases to address each assurance claim. The misuse cases as they relate to the assurance claims can be found on lucidchart located https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23. The development within these misuse cases allowed this team to develop the following categorized security requirements.

<h4><b>Confidentiality</b></h4>
<ul>
<li>Web portal must be deployed with basic login authentication</li>
<li>Web portal must include account lockout policies</li>
<li>Disable user accounts on consecutive failed attempts</li>
<li>Implement strong encryption method in authentication module</li>
<li>Web portal / command based utility must enforce secure password policies</li>
</ul>
<h4><b>Integrity</b></h4>
<ul>
<li>Web portal (admin interface) must have a username and password set up by default with no default credentials</li>
<li>Whitelisting must utilize ACL</li>
<li>Pi-Hole should implement least privilege access</li>
</ul>
<h4><b><u>Availability</b></h4>
<ul>
<li>System should save all the security logs</li>
<li>Log all DNS query attempts</li>
<li>Must include backup and recovery options for crucial files (example: password file)</li>
<li>Applies recent security patches to dependent packages</li>
<li>A user must be able to conduct future updates of the software</li>
</ul>
</br>
Reviewing the security requirements of the open source project Pi-Hole, following are the required additional security requirements related to the authentication and access control:
<ul>    
<li>Implementing Access Control prevents unauthorized access: access control attempts to bypass securities measures implemented by the system. This can be seen here https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23
</li>

<li>Access control attacks involve stealing user credentials. Once successful, the attacker may launch impersonation attack by claiming as legitimate user. Implementing least privileges access may prevent unauthorized users to have access into the system
Account lockout to mitigate brute force attacks. This can be seen here https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23
</li>
<li>Account lockout is a critical measure to overcome brute force attack. Brute force attack attempts to discover administrator’s password by trying possible combinations of letters, numbers, and symbols. Implementing account lockout after certain of attempts will strongly mitigate the attack. This can be seen here https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23
</li>
<li>Input validation to mitigate dictionary attacks: Input validation verifies that the value given by the user matches the expectation before any further processing. Input validation verifies different characters within field.
Back up recovery prevents unauthorized alteration. Back up will prevent failures when updates are not successful. It will recover the device in certain point of time when failures occur. This can be seen here https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23
</li>
</ul>

Open Source Project Pi-hole Documentation review
------------------------------------------------

This project can be found at https://pi-hole.net

The Pi-hole service is both a local DNS server and a web portal and the securing of these various functions is key for consumers who wish to place the devices on their internal network. Comparing the first assurance claim which is that the Pi-hole has no exploitable HTTP weakness the group looked at what features were utilized to enable this feature. The web interface was first established in version 2.1 as a default service. The Pi-hole team decided to utilize Lighttpd as the web service as it is advertised as a secure service. Lighttpd encourages its open source community to review its product and to recommend changes for stability and security. Pi-hole pushes out updates from Lighttpd and also encourages its community to review the Pi-hole platform as well. These two sources of review allow Pi-hole to provide a web portal service with a minimized attack surface.

Reviewing the Pi-hole open source software project allows a user to see to type of community that this project attracts. The project has been a fan based project and is providing a service that fairly unique. For one the members of the Pi-hole community are united in the desire of blocking ads by utilizing a device connected to the users’ home network. The user of this software is more likely going to be somewhat familiar with basic networking concepts. The open source project is also focusing on low powered computers like a raspberry pi which allows the software to be deployed on multiple Linux distributions natively. With all of this combined the user base for this software appears to be more willing to contribute to both stability and feature development which appears to be the case with the number of contributors to this project which is currently 76. These members are encouraged by the Pi-hole developers to communicate and desired features or requests.

To provide DNS service, Pi-hole uses dnsmasq present in most linux distros. All queries are also saved to a log file (/var/log/pihole.log) and are presented to the user through the web interface in an organized fashion. This could allow an experienced user to detect anomalous queries and take action.

Following are the observations after going through the existing documentation of Pi-Hole regarding the authentication mechanism:<ul>
   <li>Authentication: It does not have enough documentation regarding the authentication of users</li>
   <li>Password Policy: It does not have any details about the new password policy for the users</li>
   <li>Account lock / Password Reset: It does not have much details about password reset policy and account lock conditions</li>
   <li>Acknowledging the Strength of the Password: It does not have any details regarding how it measures the password strength</li>
</ul>

Open Source Project Pi-hole security installation and configuration
--------------------------------------------------------------------
Reviewing the installation procedures and how the security relates to this is quite the opposite as the initial installation method given was to run a <curl> script which is "curl -sSL https://install.pi-hole.net | bash". Even the website states that piping this to bash is dangerous and encourages the user to review the code before running it but this will introduce a complacency for users who begin to trust the marketing name Pi-hole and land on a phishing portal mimicking the Pi-hole website and the user runs a malicious script within bash. Even today the website recommends new users run this curl script into bash. This complacency allows the products "good name" to be utilized by a phishing site and users who have utilized this instillation method in the past would not be concerned when asked to run this script once again.

The configuration of the Pi-hole software utilizes shell script which is very human readable based on the configuration files. This makes it easier for users with limited coding backgrounds to review settings and configurations within each file associated with the Pi-hole software. The ad blocking domains for example are simply HOST file locations and the user can include the location of any HOST file they choose. Alternatively, the user can create their own HOSTS file based on the users own traffic by utilizing the web portal to the software. The application of easy review of the configuration files and of the creation of HOSTS files makes the user have adequate control to administer the system and to conduct a user level audit with a limited coding background. This simple feature allows users of all backgrounds to develop a trust of this open source software and allows the user to be aware of how it operates.
