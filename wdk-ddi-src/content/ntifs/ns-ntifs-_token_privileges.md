---
UID: NS:ntifs._TOKEN_PRIVILEGES
title: _TOKEN_PRIVILEGES (ntifs.h)
description: TOKEN_PRIVILEGES contains information about a set of privileges for an access token.
old-location: ifsk\token_privileges.htm
tech.root: ifsk
ms.assetid: f2f4b2b7-bec0-42c3-904b-cbc74ca76bb3
ms.date: 04/16/2018
ms.keywords: "*PTOKEN_PRIVILEGES, PTOKEN_PRIVILEGES, PTOKEN_PRIVILEGES structure pointer [Installable File System Drivers], TOKEN_PRIVILEGES, TOKEN_PRIVILEGES structure [Installable File System Drivers], _TOKEN_PRIVILEGES, ifsk.token_privileges, ntifs/PTOKEN_PRIVILEGES, ntifs/TOKEN_PRIVILEGES, securitystructures_3da1d9ba-6fa7-4b16-bdd7-416890b57f7e.xml"
f1_keywords:
 - "ntifs/TOKEN_PRIVILEGES"
req.header: ntifs.h
req.include-header: Ntifs.h
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
- TOKEN_PRIVILEGES
product:
- Windows
targetos: Windows
req.typenames: TOKEN_PRIVILEGES, *PTOKEN_PRIVILEGES
---

# _TOKEN_PRIVILEGES structure


## -description


TOKEN_PRIVILEGES contains information about a set of privileges for an access token. 


## -struct-fields




### -field PrivilegeCount

Specifies the number of entries in the <b>Privileges</b> array. 


### -field Privileges

Specifies an array of LUID_AND_ATTRIBUTES structures. Each structure contains the LUID and attributes of a privilege. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_luid_and_attributes">LUID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sefiltertoken">SeFilterToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

