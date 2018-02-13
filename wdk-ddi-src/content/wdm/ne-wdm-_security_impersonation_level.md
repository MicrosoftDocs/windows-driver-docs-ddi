---
UID: NE:wdm._SECURITY_IMPERSONATION_LEVEL
title: "_SECURITY_IMPERSONATION_LEVEL"
author: windows-driver-content
description: The SECURITY_IMPERSONATION_LEVEL enumeration type contains values that specify security impersonation levels. Security impersonation levels govern the degree to which a server process can act on behalf of a client process.
old-location: ifsk\security_impersonation_level.htm
old-project: ifsk
ms.assetid: 6033b33f-74cd-4034-baff-a931b7add370
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: wdm/SecurityImpersonation, securitystructures_d049c4aa-1df4-46b1-b789-01f04e939de2.xml, _SECURITY_IMPERSONATION_LEVEL, wdm/SecurityDelegation, SECURITY_IMPERSONATION_LEVEL, SECURITY_IMPERSONATION_LEVEL enumeration [Installable File System Drivers], wdm/SECURITY_IMPERSONATION_LEVEL, ifsk.security_impersonation_level, wdm/SecurityAnonymous, SecurityIdentification, PSECURITY_IMPERSONATION_LEVEL, SecurityAnonymous, PSECURITY_IMPERSONATION_LEVEL enumeration pointer [Installable File System Drivers], wdm/SecurityIdentification, SecurityDelegation, SecurityImpersonation, *PSECURITY_IMPERSONATION_LEVEL, wdm/PSECURITY_IMPERSONATION_LEVEL
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	SECURITY_IMPERSONATION_LEVEL
product: Windows
targetos: Windows
req.typenames: SECURITY_IMPERSONATION_LEVEL, *PSECURITY_IMPERSONATION_LEVEL
req.product: Windows 10 or later.
---

# _SECURITY_IMPERSONATION_LEVEL enumeration


## -description


The <b>SECURITY_IMPERSONATION_LEVEL</b> enumeration type contains values that specify security impersonation levels. Security impersonation levels govern the degree to which a server process can act on behalf of a client process. 


## -syntax


````
typedef enum _SECURITY_IMPERSONATION_LEVEL { 
  SecurityAnonymous,
  SecurityIdentification,
  SecurityImpersonation,
  SecurityDelegation
} SECURITY_IMPERSONATION_LEVEL, *PSECURITY_IMPERSONATION_LEVEL;
````


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

<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\wdm\ns-wdm-_privilege_set.md">PRIVILEGE_SET</a>



<a href="..\ntifs\ns-ntifs-_sid_and_attributes.md">SID_AND_ATTRIBUTES</a>



<a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-psimpersonateclient.md">PsImpersonateClient</a>



<a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a>



<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-psreferenceimpersonationtoken.md">PsReferenceImpersonationToken</a>



<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SECURITY_IMPERSONATION_LEVEL enumeration%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

