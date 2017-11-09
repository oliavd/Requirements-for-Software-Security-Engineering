Pi-hole Threat Model
====================

R3tr0 evaluated the open source software Pi-hole utilizing the Microsoft Threat modeling tool 2016 and the previous [misuse cases](https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23) which allowed the group to identify the threat model against the Pi-hole process. Retr0 developed a level 1 DFD which supports all threats identified within the previous misuse cases within Lucid Chart located [here.](https://www.lucidchart.com/invitations/accept/03df13bf-2fe3-4b3c-a4bb-1493b038bd23)

R3tr0 analyzed this diagram and by utilizing the STRIDE model we have identified the following threats as outlined below. 


Current Threat Model 
====================
Please refer Pi-Hole_ThreatModel.htm in the current directory.


Summary of Observations 
=======================

As a simple utility to be used on your home network to block ads, Pi-hole was not designed primarily with security in mind. After reviewing the software design based on our threat model, we have observed some security related issues that could be mitigated. Although Pi-Hole admin interface uses basic password authentication, http traffic is not encrypted nor authenticated. Using secure https can ensure password is not sent in the clear. Pi-Hole also doesn’t have any password complexity requirement. User password is the primary source of authentication and observed that Pi-Hole can accept any kind of password violating the basic authentication principles. Having a complex password requirement could thwart an attacker from guessing the password.It is Strongly recommended for Pi-Hole team to strengthen the authentication and encryption mechanisms currently being used. Finally Pi-Hole could implement integrity checks such as Hashes, Digital Signatures on whitelist and blacklist file to ensure it would not be tampered by an attacker. In Conclusion, Pi-Hole needs to improve authentication mechanism and encryption in order to make itself a secure application and resist against most of the security attacks.


