Pi-hole Threat Model
====================

R3tr0 evaluated the open source software Pi-hole utilizing the Microsoft Threat modeling tool 2016 and the previous [misuse cases](https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23) which allowed the group to identify the threat model against the Pi-hole process. Retr0 developed a level 1 DFD which supports all threats identified within the previous misuse cases within Lucid Chart located [here.](https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23)

R3tr0 analyzed this diagram and by utilizing the STRIDE model we have identified the following threats as outlined below. 

Spoofing
--------

**1.** Spoofing of the Network Traffic External Destination Entity  

*Category:*	Spoofing

Description:	Network Traffic may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Network Traffic. Consider using a standard authentication mechanism to identify the external entity.

Justification:	<no mitigation provided>

**4.** Spoofing of Destination Data Store Whitelist / Blacklist

*Category:*	Spoofing

Description:	Whitelist / Blacklist may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of Whitelist / Blacklist. Consider using a standard authentication mechanism to identify the destination data store.

Justification:	<no mitigation provided>

**6.** Spoofing the Pi-hole Process

*Category:*          Spoofing

Description:	Pi-hole may be spoofed by an attacker and this may lead to information disclosure by Network Traffic. Consider using a standard authentication mechanism to identify the destination process.

Justification:	<no mitigation provided>

**7.** Spoofing the Network Traffic External Entity

*Category:*	Spoofing

Description:	Network Traffic may be spoofed by an attacker and this may lead to unauthorized access to Pi-hole. Consider using a standard authentication mechanism to identify the external entity.

Justification:	<no mitigation provided>

**17.** Spoofing the Pi-hole Process 

Category:	Spoofing

Description:	Pi-hole may be spoofed by an attacker and this may lead to information disclosure by CLI user. Consider using a standard authentication mechanism to identify the destination process.

Justification:	<no mitigation provided>

**18.** Spoofing the CLI user External Entity  

Category:	Spoofing

Description:	CLI user may be spoofed by an attacker and this may lead to unauthorized access to Pi-hole. Consider using a standard authentication mechanism to identify the external entity.

Justification:	<no mitigation provided>

**28.** Spoofing the User External Entity 

Category:	Spoofing

Description:	Web user may be spoofed by an attacker and this may lead to unauthorized access to Pi-hole. Consider using a standard authentication mechanism to identify the external entity.

Justification:	<no mitigation provided>

**28.** Spoofing of the User External Destination Entity 

Category:	Spoofing

Description:	User may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of User. Consider using a standard authentication mechanism to identify the external entity.

Justification:	<no mitigation provided>

**30.** Spoofing the Pi-hole Process  

Category:	Spoofing

Description:	Pi-hole may be spoofed by an attacker and this may lead to information disclosure by Web user. Consider using a standard authentication mechanism to identify the destination process.

Justification:	<no mitigation provided>

**39.** Spoofing of Destination Data Store DNS log  

Category:	Spoofing

Description:	DNS log may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of DNS log. Consider using a standard authentication mechanism to identify the destination data store.

Justification:	<no mitigation provided>
          
**41.** Spoofing of the CLI user External Destination Entity  

Category:	Spoofing

Description:	CLI user may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of CLI user. Consider using a standard authentication mechanism to identify the external entity.

Justification:	<no mitigation provided>

**44.** Spoofing of the User External Destination Entity  

Category:	Spoofing

Description:	Web user may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Web user. Consider using a standard authentication mechanism to identify the external entity.

Justification:	<no mitigation provided>

Tampering
---------

**8.** Potential Lack of Input Validation for Pi-hole 

Category:	Tampering

Description:	Data flowing across DNS Query may be tampered with by an attacker. This may lead to a denial of service attack against Pi-hole or an elevation of privilege attack against Pi-hole or an information disclosure by Pi-hole. Failure to verify that input is as expected is a root cause of a very large number of exploitable issues. Consider all paths and the way they handle data. Verify that all input is verified for correctness using an approved list input validation approach.

Justification:	<no mitigation provided>

**19.** Potential Lack of Input Validation for Pi-hole  

Category:	Tampering

Description:	Data flowing across Input Data Flow may be tampered with by an attacker. This may lead to a denial of service attack against Pi-hole or an elevation of privilege attack against Pi-hole or an information disclosure by Pi-hole. Failure to verify that input is as expected is a root cause of a very large number of exploitable issues. Consider all paths and the way they handle data. Verify that all input is verified for correctness using an approved list input validation approach.

Justification:	<no mitigation provided>

**31.** Potential Lack of Input Validation for Pi-hole  

Category:	Tampering

Description:	Data flowing across Input HTTP Data may be tampered with by an attacker. This may lead to a denial of service attack against Pi-hole or an elevation of privilege attack against Pi-hole or an information disclosure by Pi-hole. Failure to verify that input is as expected is a root cause of a very large number of exploitable issues. Consider all paths and the way they handle data. Verify that all input is verified for correctness using an approved list input validation approach.

Justification:	<no mitigation provided>
          
Repudiation
-----------

**2.** External Entity Network Traffic Result Potentially Denies Receiving Data 

Category:	Repudiation

Description:	Network Traffic Result claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

Justification:	<no mitigation provided>

**9.** Potential Data Repudiation by Pi-hole  

Category:	Repudiation

Description:	Pi-hole claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

Justification:	<no mitigation provided>

**20.** Potential Data Repudiation by Pi-hole  

Category:	Repudiation

Description:	Pi-hole claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

Justification:	<no mitigation provided>

**32.** Potential Data Repudiation by Pi-hole  

Category:	Repudiation

Description:	Pi-hole claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

Justification:	<no mitigation provided>

**42.** External Entity CLI user Potentially Denies Receiving Data  

Category:	Repudiation

Description:	CLI user claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

Justification:	<no mitigation provided>

**45.** External Entity User Potentially Denies Receiving Data  

Category:	Repudiation

Description:	Web user claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

Justification:	<no mitigation provided>


Information Disclosure
-----------------------

**10.** Data Flow Sniffing  

Category:	Information Disclosure

Description:	Data flowing across DNS Query may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.

Justification:	DNS Query should be encrypted before it is sent to the data store.

**21.** Data Flow Sniffing  

Category:	Information Disclosure

Description:	Data flowing across Input Data Flow may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.

Justification:	<no mitigation provided>

**33.** Data Flow Sniffing  

Category:	Information Disclosure

Description:	Data flowing across Input HTTP Data may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.

Justification:	<no mitigation provided>

Denial of Service
------------------

**3.** Data Flow Block Traffic Is Potentially Interrupted  

Category:	Denial Of Service

Description:	An external agent interrupts data flowing across a trust boundary in either direction.

Justification:	<no mitigation provided>

**5.** Potential Excessive Resource Consumption for Pi-hole or Whitelist / Blacklist 

Category:	Denial Of Service

Description:	Does Pi-hole or Whitelist / Blacklist take explicit steps to control resource consumption? Resource consumption attacks can be hard to deal with, and there are times that it makes sense to let the OS do the job. Be careful that your resource requests don't deadlock, and that they do timeout.

Justification:	<no mitigation provided>

**11.** Potential Process Crash or Stop for Pi-hole  

Category:	Denial Of Service

Description:	Pi-hole crashes, halts, stops or runs slowly; in all cases violating an availability metric.

Justification:	<no mitigation provided>

**12.** Data Flow DNS Query Is Potentially Interrupted  

Category:	Denial Of Service

Description:	An external agent interrupts data flowing across a trust boundary in either direction.

Justification:	<no mitigation provided>

**22.** Potential Process Crash or Stop for Pi-hole  

Category:	Denial Of Service

Description:	Pi-hole crashes, halts, stops or runs slowly; in all cases violating an availability metric.

Justification:	<no mitigation provided>

**23.** Data Flow Input Data Flow Is Potentially Interrupted  

Category:	Denial Of Service

Description:	An external agent interrupts data flowing across a trust boundary in either direction.

Justification:	<no mitigation provided>

**34.** Potential Process Crash or Stop for Pi-hole  

Category:	Denial Of Service

Description:	Pi-hole crashes, halts, stops or runs slowly; in all cases violating an availability metric.

Justification:	Pi-hole need to ensure that it is always available and notify user in case of poor network connections or traffic load.

**33.** Data Flow Input Data Flow Is Potentially Interrupted  

Category:	Denial Of Service

Description:	An external agent interrupts data flowing across a trust boundary in either direction.

Justification:	<no mitigation provided>

**40.** Potential Excessive Resource Consumption for Pi-hole or DNS log  

Category:	Denial Of Service

Description:	Does Pi-hole or DNS log take explicit steps to control resource consumption? Resource consumption attacks can be hard to deal with, and there are times that it makes sense to let the OS do the job. Be careful that your resource requests don't deadlock, and that they do timeout.

Justification:	<no mitigation provided>
          
**43.** Data Flow Output Data Flow Is Potentially Interrupted  

Category:	Denial Of Service

Description:	An external agent interrupts data flowing across a trust boundary in either direction.

Justification:	<no mitigation provided>
          
**46.** Data Flow Output Data Flow Is Potentially Interrupted  

Category:	Denial Of Service

Description:	An external agent interrupts data flowing across a trust boundary in either direction.

Justification:	<no mitigation provided>


Elevation of Privilege
----------------------

**13.** Elevation Using Impersonation  

Category:	Elevation Of Privilege

Description:	Pi-hole may be able to impersonate the context of Network Traffic in order to gain additional privilege.

Justification:	<no mitigation provided>

**14.** Pi-hole May be Subject to Elevation of Privilege Using Remote Code Execution  

Category:	Elevation Of Privilege

Description:	Network Traffic may be able to remotely execute code for Pi-hole.

Justification:	<no mitigation provided>

**15.** Elevation by Changing the Execution Flow in Pi-hole  

Category:	Elevation Of Privilege

Description:	An attacker may pass data into Pi-hole in order to change the flow of program execution within Pi-hole to the attacker's choosing.

Justification:	<no mitigation provided>

**16.** Cross Site Request Forgery  

Category:	Elevation Of Privilege

Description:	Cross-site request forgery (CSRF or XSRF) is a type of attack in which an attacker forces a user's browser to make a forged request to a vulnerable site by exploiting an existing trust relationship between the browser and the vulnerable web site.  In a simple scenario, a user is logged in to web site A using a cookie as a credential.  The other browses to web site B.  Web site B returns a page with a hidden form that posts to web site A.  Since the browser will carry the user's cookie to web site A, web site B now can take any action on web site A, for example, adding an admin to an account.  The attack can be used to exploit any requests that the browser automatically authenticates, e.g. by session cookie, integrated authentication, IP whitelisting, …  The attack can be carried out in many ways such as by luring the victim to a site under control of the attacker, getting the user to click a link in a phishing email, or hacking a reputable web site that the victim will visit. The issue can only be resolved on the server side by requiring that all authenticated state-changing requests include an additional piece of secret payload (canary or CSRF token) which is known only to the legitimate web site and the browser and which is protected in transit through SSL/TLS. See the Forgery Protection property on the flow stencil for a list of mitigations.

Justification:	<no mitigation provided>
          
**24.** Elevation Using Impersonation  

Category:	Elevation Of Privilege

Description:	Pi-hole may be able to impersonate the context of CLI user in order to gain additional privilege.

Justification:	<no mitigation provided>

**25.** Pi-hole May be Subject to Elevation of Privilege Using Remote Code Execution  

Category:	Elevation Of Privilege

Description:	CLI user may be able to remotely execute code for Pi-hole.

Justification:	<no mitigation provided>

**26.** Elevation by Changing the Execution Flow in Pi-hole  

Category:	Elevation Of Privilege

Description:	An attacker may pass data into Pi-hole in order to change the flow of program execution within Pi-hole to the attacker's choosing.

Justification:	<no mitigation provided>

**27.** Cross Site Request Forgery

Category:	Elevation Of Privilege

Description:	Cross-site request forgery (CSRF or XSRF) is a type of attack in which an attacker forces a user's browser to make a forged request to a vulnerable site by exploiting an existing trust relationship between the browser and the vulnerable web site.  In a simple scenario, a user is logged in to web site A using a cookie as a credential.  The other browses to web site B.  Web site B returns a page with a hidden form that posts to web site A.  Since the browser will carry the user's cookie to web site A, web site B now can take any action on web site A, for example, adding an admin to an account.  The attack can be used to exploit any requests that the browser automatically authenticates, e.g. by session cookie, integrated authentication, IP whitelisting, …  The attack can be carried out in many ways such as by luring the victim to a site under control of the attacker, getting the user to click a link in a phishing email, or hacking a reputable web site that the victim will visit. The issue can only be resolved on the server side by requiring that all authenticated state-changing requests include an additional piece of secret payload (canary or CSRF token) which is known only to the legitimate web site and the browser and which is protected in transit through SSL/TLS. See the Forgery Protection property on the flow stencil for a list of mitigations.

Justification:	<no mitigation provided>

**29.** Elevation Using Impersonation

Category:	Elevation Of Privilege

Description:	Pi-hole may be able to impersonate the context of Web user in order to gain additional privilege.

Justification:	<no mitigation provided>

**36.** Pi-hole May be Subject to Elevation of Privilege Using Remote Code Execution

Category:	Elevation Of Privilege

Description:	Web user may be able to remotely execute code for Pi-hole.

Justification:	<no mitigation provided>

**37.** Elevation by Changing the Execution Flow in Pi-hole

Category:	Elevation Of Privilege

Description:	An attacker may pass data into Pi-hole in order to change the flow of program execution within Pi-hole to the attacker's choosing.

Justification:	<no mitigation provided>

**38.** Cross Site Request Forgery

Category:	Elevation Of Privilege

Description:	Cross-site request forgery (CSRF or XSRF) is a type of attack in which an attacker forces a user's browser to make a forged request to a vulnerable site by exploiting an existing trust relationship between the browser and the vulnerable web site.  In a simple scenario, a user is logged in to web site A using a cookie as a credential.  The other browses to web site B.  Web site B returns a page with a hidden form that posts to web site A.  Since the browser will carry the user's cookie to web site A, web site B now can take any action on web site A, for example, adding an admin to an account.  The attack can be used to exploit any requests that the browser automatically authenticates, e.g. by session cookie, integrated authentication, IP whitelisting, …  The attack can be carried out in many ways such as by luring the victim to a site under control of the attacker, getting the user to click a link in a phishing email, or hacking a reputable web site that the victim will visit. The issue can only be resolved on the server side by requiring that all authenticated state-changing requests include an additional piece of secret payload (canary or CSRF token) which is known only to the legitimate web site and the browser and which is protected in transit through SSL/TLS. See the Forgery Protection property on the flow stencil for a list of mitigations.

Justification:	<no mitigation provided>







Current threat model 
====================
<p align="center">
<img src="https://user-images.githubusercontent.com/30883926/32528774-7e9d3354-c3fa-11e7-99f2-f18fb91a2736.png">
</p>


</style></head><body><h1 class="title" tabindex="0">Threat Modeling Report</h1><span tabindex="0">
          Created on 11/8/2017 5:00:00 PM</span><p tabindex="0"><strong>Threat Model Name: Pi-hole Threat Model</strong></p><p tabindex="0"><strong>Owner: Michael Galde </strong></p><p tabindex="0"><strong>Reviewer: </strong></p><p tabindex="0"><strong>Contributors: R3tr0 </strong></p><p tabindex="0"><strong>Description: A threat model utilizing mis-use cases of the open source software Pi-hole </strong></p><p tabindex="0"><strong>Assumptions: A fresh install of Pi-hole within a home network </strong></p><p tabindex="0"><strong>External Dependencies: </strong></p><br /><h3 tabindex="0">Threat Model Summary:</h3><table><tr tabindex="0" role="row"><td>Not Started</td><td>46</td></tr><tr tabindex="0" role="row"><td>Not Applicable</td><td>0</td></tr><tr tabindex="0" role="row"><td>Needs Investigation</td><td>0</td></tr><tr tabindex="0" role="row"><td>Mitigation Implemented</td><td>0</td></tr><tr tabindex="0" role="row"><td>Total</td><td>46</td></tr><tr tabindex="0" role="row"><td>Total Migrated</td><td>0</td></tr></table><p class="bugtrack" /><hr /><h2 tabindex="0">
            Diagram: Diagram 1</h2><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528774-7e9d3354-c3fa-11e7-99f2-f18fb91a2736.png"/><h3 tabindex="0">Diagram 1 Diagram Summary:
          </h3><table><tr tabindex="0" role="row"><td>Not Started</td><td>46</td></tr><tr tabindex="0" role="row"><td>Not Applicable</td><td>0</td></tr><tr tabindex="0" role="row"><td>Needs Investigation</td><td>0</td></tr><tr tabindex="0" role="row"><td>Mitigation Implemented</td><td>0</td></tr><tr tabindex="0" role="row"><td>Total</td><td>46</td></tr><tr tabindex="0" role="row"><td>Total Migrated</td><td>0</td></tr></table><h3 tabindex="0">
      Interaction: Block / Pass Traffic</h3><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528800-9d51760c-c3fa-11e7-9a99-32324b62163a.png" /><div class="threat"><h4 tabindex="0" id="&#xA;          t1"><span>1. Spoofing of the Network Traffic External Destination Entity</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Network Traffic may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Network Traffic. Consider using a standard authentication mechanism to identify the external entity.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t2"><span>2. External Entity Network Traffic Potentially Denies Receiving Data</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Repudiation</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Network Traffic claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t3"><span>3. Data Flow Block / Pass Traffic Is Potentially Interrupted</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An external agent interrupts data flowing across a trust boundary in either direction.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><br /><h3 tabindex="0">
      Interaction: Compare Check</h3><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528833-cebfb208-c3fa-11e7-9104-95cd48bc6269.png"/><div class="threat"><h4 tabindex="0" id="&#xA;          t4"><span>4. Spoofing of Destination Data Store Whitelist / Blacklist</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Whitelist / Blacklist may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of Whitelist / Blacklist. Consider using a standard authentication mechanism to identify the destination data store.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t5"><span>5. Potential Excessive Resource Consumption for Pi-hole or Whitelist / Blacklist</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Does Pi-hole or Whitelist / Blacklist take explicit steps to control resource consumption? Resource consumption attacks can be hard to deal with, and there are times that it makes sense to let the OS do the job. Be careful that your resource requests don't deadlock, and that they do timeout.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><br /><h3 tabindex="0">
      Interaction: DNS Query</h3><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528861-f6f74bdc-c3fa-11e7-89db-17dc5fccb378.png" /><div class="threat"><h4 tabindex="0" id="&#xA;          t6"><span>6. Spoofing the Pi-hole Process</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole may be spoofed by an attacker and this may lead to information disclosure by Network Traffic. Consider using a standard authentication mechanism to identify the destination process.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t7"><span>7. Spoofing the Network Traffic External Entity</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Network Traffic may be spoofed by an attacker and this may lead to unauthorized access to Pi-hole. Consider using a standard authentication mechanism to identify the external entity.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t8"><span>8. Potential Lack of Input Validation for Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Tampering</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Data flowing across DNS Query may be tampered with by an attacker. This may lead to a denial of service attack against Pi-hole or an elevation of privilege attack against Pi-hole or an information disclosure by Pi-hole. Failure to verify that input is as expected is a root cause of a very large number of exploitable issues. Consider all paths and the way they handle data. Verify that all input is verified for correctness using an approved list input validation approach.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t9"><span>9. Potential Data Repudiation by Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Repudiation</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t10"><span>10. Data Flow Sniffing</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Information Disclosure</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Data flowing across DNS Query may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t11"><span>11. Potential Process Crash or Stop for Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole crashes, halts, stops or runs slowly; in all cases violating an availability metric.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t12"><span>12. Data Flow DNS Query Is Potentially Interrupted</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An external agent interrupts data flowing across a trust boundary in either direction.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t13"><span>13. Elevation Using Impersonation</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole may be able to impersonate the context of Network Traffic in order to gain additional privilege.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t14"><span>14. Pi-hole May be Subject to Elevation of Privilege Using Remote Code Execution</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Network Traffic may be able to remotely execute code for Pi-hole.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t15"><span>15. Elevation by Changing the Execution Flow in Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An attacker may pass data into Pi-hole in order to change the flow of program execution within Pi-hole to the attacker's choosing.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t16"><span>16. Cross Site Request Forgery</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Cross-site request forgery (CSRF or XSRF) is a type of attack in which an attacker forces a user's browser to make a forged request to a vulnerable site by exploiting an existing trust relationship between the browser and the vulnerable web site.  In a simple scenario, a user is logged in to web site A using a cookie as a credential.  The other browses to web site B.  Web site B returns a page with a hidden form that posts to web site A.  Since the browser will carry the user's cookie to web site A, web site B now can take any action on web site A, for example, adding an admin to an account.  The attack can be used to exploit any requests that the browser automatically authenticates, e.g. by session cookie, integrated authentication, IP whitelisting, …  The attack can be carried out in many ways such as by luring the victim to a site under control of the attacker, getting the user to click a link in a phishing email, or hacking a reputable web site that the victim will visit. The issue can only be resolved on the server side by requiring that all authenticated state-changing requests include an additional piece of secret payload (canary or CSRF token) which is known only to the legitimate web site and the browser and which is protected in transit through SSL/TLS. See the Forgery Protection property on the flow stencil for a list of mitigations.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><br /><h3 tabindex="0">
      Interaction: Input Data Flow</h3><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528910-1e01259a-c3fb-11e7-8db6-2ec2495c026a.png" /><div class="threat"><h4 tabindex="0" id="&#xA;          t17"><span>17. Spoofing the Pi-hole Process</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole may be spoofed by an attacker and this may lead to information disclosure by CLI user. Consider using a standard authentication mechanism to identify the destination process.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t18"><span>18. Spoofing the CLI user External Entity</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">CLI user may be spoofed by an attacker and this may lead to unauthorized access to Pi-hole. Consider using a standard authentication mechanism to identify the external entity.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t19"><span>19. Potential Lack of Input Validation for Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Tampering</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Data flowing across Input Data Flow may be tampered with by an attacker. This may lead to a denial of service attack against Pi-hole or an elevation of privilege attack against Pi-hole or an information disclosure by Pi-hole. Failure to verify that input is as expected is a root cause of a very large number of exploitable issues. Consider all paths and the way they handle data. Verify that all input is verified for correctness using an approved list input validation approach.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t20"><span>20. Potential Data Repudiation by Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Repudiation</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t21"><span>21. Data Flow Sniffing</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Information Disclosure</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Data flowing across Input Data Flow may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t22"><span>22. Potential Process Crash or Stop for Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole crashes, halts, stops or runs slowly; in all cases violating an availability metric.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t23"><span>23. Data Flow Input Data Flow Is Potentially Interrupted</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An external agent interrupts data flowing across a trust boundary in either direction.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t24"><span>24. Elevation Using Impersonation</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole may be able to impersonate the context of CLI user in order to gain additional privilege.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t25"><span>25. Pi-hole May be Subject to Elevation of Privilege Using Remote Code Execution</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">CLI user may be able to remotely execute code for Pi-hole.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t26"><span>26. Elevation by Changing the Execution Flow in Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An attacker may pass data into Pi-hole in order to change the flow of program execution within Pi-hole to the attacker's choosing.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t27"><span>27. Cross Site Request Forgery</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Cross-site request forgery (CSRF or XSRF) is a type of attack in which an attacker forces a user's browser to make a forged request to a vulnerable site by exploiting an existing trust relationship between the browser and the vulnerable web site.  In a simple scenario, a user is logged in to web site A using a cookie as a credential.  The other browses to web site B.  Web site B returns a page with a hidden form that posts to web site A.  Since the browser will carry the user's cookie to web site A, web site B now can take any action on web site A, for example, adding an admin to an account.  The attack can be used to exploit any requests that the browser automatically authenticates, e.g. by session cookie, integrated authentication, IP whitelisting, …  The attack can be carried out in many ways such as by luring the victim to a site under control of the attacker, getting the user to click a link in a phishing email, or hacking a reputable web site that the victim will visit. The issue can only be resolved on the server side by requiring that all authenticated state-changing requests include an additional piece of secret payload (canary or CSRF token) which is known only to the legitimate web site and the browser and which is protected in transit through SSL/TLS. See the Forgery Protection property on the flow stencil for a list of mitigations.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><br /><h3 tabindex="0">
      Interaction: Input HTTP Data</h3><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528933-38aff60a-c3fb-11e7-8e56-01ca9f4b22c3.png" /><div class="threat"><h4 tabindex="0" id="&#xA;          t28"><span>28. Spoofing the User External Entity</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Web user may be spoofed by an attacker and this may lead to unauthorized access to Pi-hole. Consider using a standard authentication mechanism to identify the external entity.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t29"><span>29. Elevation Using Impersonation</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole may be able to impersonate the context of Web user in order to gain additional privilege.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t30"><span>30. Spoofing the Pi-hole Process</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole may be spoofed by an attacker and this may lead to information disclosure by Web user. Consider using a standard authentication mechanism to identify the destination process.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t31"><span>31. Potential Lack of Input Validation for Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Tampering</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Data flowing across Input HTTP Data may be tampered with by an attacker. This may lead to a denial of service attack against Pi-hole or an elevation of privilege attack against Pi-hole or an information disclosure by Pi-hole. Failure to verify that input is as expected is a root cause of a very large number of exploitable issues. Consider all paths and the way they handle data. Verify that all input is verified for correctness using an approved list input validation approach.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t32"><span>32. Potential Data Repudiation by Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Repudiation</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t33"><span>33. Data Flow Sniffing</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Information Disclosure</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Data flowing across Input HTTP Data may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t34"><span>34. Potential Process Crash or Stop for Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Pi-hole crashes, halts, stops or runs slowly; in all cases violating an availability metric.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t35"><span>35. Data Flow Input Data Flow Is Potentially Interrupted</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An external agent interrupts data flowing across a trust boundary in either direction.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t36"><span>36. Pi-hole May be Subject to Elevation of Privilege Using Remote Code Execution</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Web user may be able to remotely execute code for Pi-hole.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t37"><span>37. Elevation by Changing the Execution Flow in Pi-hole</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An attacker may pass data into Pi-hole in order to change the flow of program execution within Pi-hole to the attacker's choosing.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t38"><span>38. Cross Site Request Forgery</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Elevation Of Privilege</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Cross-site request forgery (CSRF or XSRF) is a type of attack in which an attacker forces a user's browser to make a forged request to a vulnerable site by exploiting an existing trust relationship between the browser and the vulnerable web site.  In a simple scenario, a user is logged in to web site A using a cookie as a credential.  The other browses to web site B.  Web site B returns a page with a hidden form that posts to web site A.  Since the browser will carry the user's cookie to web site A, web site B now can take any action on web site A, for example, adding an admin to an account.  The attack can be used to exploit any requests that the browser automatically authenticates, e.g. by session cookie, integrated authentication, IP whitelisting, …  The attack can be carried out in many ways such as by luring the victim to a site under control of the attacker, getting the user to click a link in a phishing email, or hacking a reputable web site that the victim will visit. The issue can only be resolved on the server side by requiring that all authenticated state-changing requests include an additional piece of secret payload (canary or CSRF token) which is known only to the legitimate web site and the browser and which is protected in transit through SSL/TLS. See the Forgery Protection property on the flow stencil for a list of mitigations.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><br /><h3 tabindex="0">
      Interaction: InputData Flow</h3><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528952-4f2b25d0-c3fb-11e7-8bd7-60a747d9aa7f.png" /><div class="threat"><h4 tabindex="0" id="&#xA;          t39"><span>39. Spoofing of Destination Data Store DNS log</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">DNS log may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of DNS log. Consider using a standard authentication mechanism to identify the destination data store.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t40"><span>40. Potential Excessive Resource Consumption for Pi-hole or DNS log</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Does Pi-hole or DNS log take explicit steps to control resource consumption? Resource consumption attacks can be hard to deal with, and there are times that it makes sense to let the OS do the job. Be careful that your resource requests don't deadlock, and that they do timeout.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><br /><h3 tabindex="0">
      Interaction: Output Data Flow</h3><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528980-6d2dde4c-c3fb-11e7-87d1-4b7ac88ce41b.png" /><div class="threat"><h4 tabindex="0" id="&#xA;          t41"><span>41. Spoofing of the CLI user External Destination Entity</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">CLI user may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of CLI user. Consider using a standard authentication mechanism to identify the external entity.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t42"><span>42. External Entity CLI user Potentially Denies Receiving Data</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Repudiation</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">CLI user claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t43"><span>43. Data Flow Output Data Flow Is Potentially Interrupted</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An external agent interrupts data flowing across a trust boundary in either direction.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><br /><h3 tabindex="0">
      Interaction: Output HTTP Data </h3><img tabindex="0" src="https://user-images.githubusercontent.com/30883926/32528995-83f08e4a-c3fb-11e7-9ae1-1ef412e566c4.png" /><div class="threat"><h4 tabindex="0" id="&#xA;          t44"><span>44. Spoofing of the User External Destination Entity</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Spoofing</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Web user may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Web user. Consider using a standard authentication mechanism to identify the external entity.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t45"><span>45. External Entity User Potentially Denies Receiving Data</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Repudiation</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">Web user claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><div class="threat"><h4 tabindex="0" id="&#xA;          t46"><span>46. Data Flow Output Data Flow Is Potentially Interrupted</span> 
        [State: Not Started] 
        [Priority: High] 
        </h4><table role="grid"><tr><td id="threat-title-category" role="rowheader" tabindex="0"><strong>Category:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-category">Denial Of Service</td></tr><tr><td id="threat-title-description" role="rowheader" tabindex="0"><strong>Description:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-description">An external agent interrupts data flowing across a trust boundary in either direction.</td></tr><tr><td id="threat-title-justification" role="rowheader" tabindex="0"><strong>Justification:</strong></td><td class="infotd" tabindex="0" role="gridcell" headers="threat-title-justification">&lt;no mitigation provided&gt;</td></tr></table></div><br /></body></html>
