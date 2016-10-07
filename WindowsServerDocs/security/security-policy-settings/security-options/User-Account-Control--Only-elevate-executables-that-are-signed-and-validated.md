---
title: User Account Control: Only elevate executables that are signed and validated
description: "Windows Server Security"
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: security-policy-settings
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5dc883c0-a83e-4a42-a750-8767f4f79f78
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
---
# User Account Control: Only elevate executables that are signed and validated

>Applies To: Windows Server&reg; 2016, Windows Server&reg; 2012 R2, Windows Server&reg; 2012

This security policy reference topic for the IT professional describes the best practices, location, values, policy management and security considerations for this policy setting.  
  
## Reference  
This policy setting enforces public key infrastructure (PKI) signature checks on any interactive application that requests elevation of privilege. Enterprise administrators can control the applications that are allowed to run through the population of certificates in the local computer's Trusted Publishers store.  
  
A trusted publisher is a certificate issuer that the computer’s user has chosen to trust and that has certificate details that have been added to the store of trusted publishers.  
  
The Windows operating system maintains certificates in certificate stores. These stores can be represented by containers in the file system or the registry, or they can be implemented as physical stores such as smart cards. Certificate stores are associated with the computer object or they are owned by a distinct user who has a security context and profile on that computer. In addition, services can have certificate stores. A certificate store will often contain numerous certificates, possibly issued from a number of different certification authorities (CAs).  
  
When certificate path discovery is initiated, the Windows operating system attempts to locate the issuing CA for the certificates, and it builds a certificate path to the trusted root certificate. Intermediate certificates are included as part of the application protocol or are picked up from Group Policy or through URLs that are specified in the Authority Information Access (AIA) extension. When the path is built, each certificate in the path is verified for validity with respect to various parameters, such as name, time, signature, revocation status, and other constraints.  
  
### Possible values  
  
-   Enabled  
  
    Enforces the PKI certificate chain validation of a given executable file before it is permitted to run.  
  
-   Disabled  
  
    Does not enforce PKI certificate chain validation before a given executable file is permitted to run.  
  
### Best practices  
  
1.  Best practices are dependent on your security and performance goals.  
  
### Location  
*GPO_name*\Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options  
  
### Default values  
The following table lists the actual and effective default values for this policy. Default values are also listed on the policy’s property page.  
  
|Server type or GPO|Default value|  
|----------------------|-----------------|  
|Default Domain Policy|Not defined|  
|Default Domain Controller Policy|Not defined|  
|Stand-Alone Server Default Settings|Disabled|  
|DC Effective Default Settings|Disabled|  
|Member Server Effective Default Settings|Disabled|  
|Client Computer Effective Default Settings|Disabled|  
  
### Operating system version differences  
There are no differences in this policy between operating systems beginning with Windows Vista and Windows Server 2008.  
  
## Policy management  
This section describes features and tools that are available to help you manage this policy.  
  
### Restart requirement  
None. Changes to this policy become effective without a computer restart when they are saved locally or distributed through Group Policy.  
  
### Group Policy  
Distributing this policy through Group Policy to operating systems earlier than Windows Vista and Windows Server 2008 will have no impact (because UAC was first introduced in Windows Vista).  
  
## Security considerations  
This section describes how an attacker might exploit a feature or its configuration, how to implement the countermeasure, and the possible negative consequences of countermeasure implementation.  
  
### Vulnerability  
Intellectual property, personally identifiable information, and other confidential data are normally manipulated by applications on the computer, and elevated credentials are required to access the information. Users and administrators inherently trust applications that are used with these information sources, and they provide their credentials. If one of these applications is replaced by a rogue application that appears identical to the trusted application, the confidential data could be compromised and the user's administrative credentials would also be compromised.  
  
### Countermeasure  
Enable the **User Account Control: Only elevate executables that are signed and validated**.  
  
### Potential impact  
Enabling this setting requires that you have a PKI infrastructure and that your enterprise administrators have populated the Trusted Publishers store with the certificates for the allowed applications. Some older applications are not signed, and they cannot be used in an environment that is hardened with this setting. You should carefully test your applications in a preproduction environment before implementing this setting.  
  
Control over the applications that are installed on the desktops and the hardware that joins your domain should provide similar protection from the vulnerability that is addressed by this setting. Additionally, the level of protection that is provided by this setting is not an assurance that all rogue applications will be found.  
  
