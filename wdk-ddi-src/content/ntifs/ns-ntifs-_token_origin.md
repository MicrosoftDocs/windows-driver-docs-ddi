---
UID: NS:ntifs._TOKEN_ORIGIN
title: "_TOKEN_ORIGIN"
author: windows-driver-content
description: The TOKEN_ORIGIN structure contains information about the origin of the logon session.
old-location: ifsk\token_origin.htm
old-project: ifsk
ms.assetid: 6e2175f3-3d63-40d0-854b-440862530aa8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_ORIGIN, PTOKEN_ORIGIN, PTOKEN_ORIGIN structure pointer [Installable File System Drivers], TOKEN_ORIGIN, TOKEN_ORIGIN structure [Installable File System Drivers], _TOKEN_ORIGIN, ifsk.token_origin, ntifs/PTOKEN_ORIGIN, ntifs/TOKEN_ORIGIN, securitystructures_5cc2fc36-4e83-4544-8f24-dcbf768dbb9c.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	TOKEN_ORIGIN
product: Windows
targetos: Windows
req.typenames: TOKEN_ORIGIN, *PTOKEN_ORIGIN
---

# _TOKEN_ORIGIN structure


## -description


The TOKEN_ORIGIN structure contains information about the origin of the logon session. 


## -syntax


````
typedef struct _TOKEN_ORIGIN {
  LUID OriginatingLogonSession;
} TOKEN_ORIGIN, *PTOKEN_ORIGIN;
````


## -struct-fields




### -field OriginatingLogonSession

The locally unique identifier (LUID) for the logon session. If the token resulted from a logon using explicit credentials, such as passing name, domain, and password to the user-mode <b>LogonUser</b> function, then this member will contain the ID of the logon session that created it. If the token resulted from network authentication, such as a call to the user-mode <b>AcceptSecurityContext</b>, or a call to the user-mode <b>LogonUser</b> function with dwLogonType set to LOGON32_LOGON_NETWORK or LOGON32_LOGON_NETWORK_CLEARTEXT, then this member will be zero. 


## -remarks



The TOKEN_ORIGIN structure is available on Windows Server 2003 or later.




## -see-also

<a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_ORIGIN structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

