---
UID: NE:wdm._SECURITY_IMPERSONATION_LEVEL
title: "_SECURITY_IMPERSONATION_LEVEL"
author: windows-driver-content
description: The SECURITY_IMPERSONATION_LEVEL enumeration type contains values that specify security impersonation levels. Security impersonation levels govern the degree to which a server process can act on behalf of a client process.
old-location: ifsk\security_impersonation_level.htm
old-project: ifsk
ms.assetid: 6033b33f-74cd-4034-baff-a931b7add370
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSECURITY_IMPERSONATION_LEVEL, PSECURITY_IMPERSONATION_LEVEL, PSECURITY_IMPERSONATION_LEVEL enumeration pointer [Installable File System Drivers], SECURITY_IMPERSONATION_LEVEL, SECURITY_IMPERSONATION_LEVEL enumeration [Installable File System Drivers], SecurityAnonymous, SecurityDelegation, SecurityIdentification, SecurityImpersonation, _SECURITY_IMPERSONATION_LEVEL, ifsk.security_impersonation_level, securitystructures_d049c4aa-1df4-46b1-b789-01f04e939de2.xml, wdm/PSECURITY_IMPERSONATION_LEVEL, wdm/SECURITY_IMPERSONATION_LEVEL, wdm/SecurityAnonymous, wdm/SecurityDelegation, wdm/SecurityIdentification, wdm/SecurityImpersonation"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	SECURITY_IMPERSONATION_LEVEL
product: Windows
targetos: Windows
req.typenames: SECURITY_IMPERSONATION_LEVEL, *PSECURITY_IMPERSONATION_LEVEL
req.product: Windows 10 or later.
---

# _SECURITY_IMPERSONATION_LEVEL enumeration


## -description


The <b>SECURITY_IMPERSONATION_LEVEL</b> enumeration type contains values that specify security impersonation levels. Security impersonation levels govern the degree to which a server process can act on behalf of a client process. 


## -enum-fields




### -field SecurityAnonymous

The server process cannot obtain identification information about the client and it cannot impersonate the client. It is defined with no value given, and thus, by ANSI C rules, defaults to a value of zero. 


### -field SecurityIdentification

The server process can obtain information about the client, such as security identifiers and privileges, but it cannot impersonate the client. This is useful for servers that export their own objects -- for example, database products that export tables and views. Using the retrieved client-security information, the server can make access-validation decisions without being able to utilize other services using the client's security context. 


### -field SecurityImpersonation

The server process can impersonate the client's security context on its local system. The server cannot impersonate the client on remote systems. 


### -field SecurityDelegation

The server process can impersonate the client's security context on remote systems. 

 This impersonation level is supported starting with Windows 2000.


## -remarks



Impersonation is the ability of a process to take on the security attributes of another process.

<div class="alert"><b>Note</b>  Be aware of the following derived types:<pre class="syntax" xml:space="preserve"><code>#define DEFAULT_IMPERSONATION_LEVEL SecurityImpersonation
#define SECURITY_MAX_IMPERSONATION_LEVEL SecurityDelegation
#define SECURITY_MIN_IMPERSONATION_LEVEL SecurityAnonymous // Windows XP and later only</code></pre>
</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549716">LUID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551860">PRIVILEGE_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551907">PsImpersonateClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551929">PsReferenceImpersonationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563674">SeAccessCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>
 

 

