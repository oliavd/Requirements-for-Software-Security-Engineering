Open Source Project:  Pi-hole
========

Authors:  
<ul>            
<li>Michael Galde </li>
<li>Carmel Waka </li>
<li>Olivier Avande</li>
<li>Srikanth Vadla</li>
</ul>

Team Name: R3tr0
------------------

"R3tr0" identified that the open source project Pi-hole utilizes shell script for 81% of its code. Shell scripting is mentioned in multiple Linux forums and is often compared to Microsoft Windows .bat files, however, as Pi-hole demonstrates, shell scripting is a powerful programing language that can help a user save time and learn bash commands in context and avoid learning yet another programing language. 

The Pi-hole service that is created utilizes the onboard dnsmasq service which is a lightweight DNS forwarder. Dnsmasq provides Domain Name System (DNS) forwarding, Dynamic Host Configuration Protocol (DHCP), router advertisement and network boot features for small computer networks. Pi-hole however utilizes this service to add a white-list / black-list feature which is then used to block advertisements or entire domains within a home network. Essentially making your entire home network capable of blocking advertisements like a computer with uBlock Origin.

"R3tr0" conducted a manual code review of the open source Pi-hole project and have developed the following observations based on this review. Following the threat model report which can be found [here](/Threat-Model/Report.md), R3tr0 identified three external boundaries that fall within the Pi-hole process. External network traffic, Command line user interface and the web user interface were identified as external boundaries. 

R3tr0 found a automated shell script checker which worked great for our project called [Shell Check](https://www.shellcheck.net/). Shell check is a Haskell program that does real time code analysis and is currently used within vim, emacs, sublime, atom, VSCode and other GCC editors. Shell Check can recognize several types of incorrect quoting, many types of incorrect test statements, recognize instances where commands are used incorrectly and recognizes many common beginner syntax errors. Shell check is used as a static analysis tool.
