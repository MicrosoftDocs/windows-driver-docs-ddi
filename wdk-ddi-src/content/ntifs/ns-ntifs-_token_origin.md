---
UID: NS:ntifs._TOKEN_ORIGIN
title: _TOKEN_ORIGIN (ntifs.h)
description: The TOKEN_ORIGIN structure contains information about the origin of the logon session.
old-location: ifsk\token_origin.htm
tech.root: ifsk
ms.assetid: 6e2175f3-3d63-40d0-854b-440862530aa8
ms.date: 04/16/2018
keywords: ["_TOKEN_ORIGIN structure"]
ms.keywords: "*PTOKEN_ORIGIN, PTOKEN_ORIGIN, PTOKEN_ORIGIN structure pointer [Installable File System Drivers], TOKEN_ORIGIN, TOKEN_ORIGIN structure [Installable File System Drivers], _TOKEN_ORIGIN, ifsk.token_origin, ntifs/PTOKEN_ORIGIN, ntifs/TOKEN_ORIGIN, securitystructures_5cc2fc36-4e83-4544-8f24-dcbf768dbb9c.xml"
f1_keywords:
 - "ntifs/TOKEN_ORIGIN"
 - "TOKEN_ORIGIN"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- TOKEN_ORIGIN
targetos: Windows
req.typenames: TOKEN_ORIGIN, *PTOKEN_ORIGIN
---

# _TOKEN_ORIGIN structure


## -description


The TOKEN_ORIGIN structure contains information about the origin of the logon session. 


## -struct-fields




### -field OriginatingLogonSession

The locally unique identifier (LUID) for the logon session. If the token resulted from a logon using explicit credentials, such as passing name, domain, and password to the user-mode <b>LogonUser</b> function, then this member will contain the ID of the logon session that created it. If the token resulted from network authentication, such as a call to the user-mode <b>AcceptSecurityContext</b>, or a call to the user-mode <b>LogonUser</b> function with dwLogonType set to LOGON32_LOGON_NETWORK or LOGON32_LOGON_NETWORK_CLEARTEXT, then this member will be zero. 


## -remarks



The TOKEN_ORIGIN structure is available on Windows Server 2003 or later.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_luid_and_attributes">LUID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sefiltertoken">SeFilterToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisrestricted">SeTokenIsRestricted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

