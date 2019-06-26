---
UID: NS:ntifs._TOKEN_STATISTICS
title: _TOKEN_STATISTICS (ntifs.h)
description: TOKEN_STATISTICS contains information about an access token. A driver can retrieve this information by calling SeQueryInformationToken or ZwQueryInformationToken.
old-location: ifsk\token_statistics.htm
tech.root: ifsk
ms.assetid: a7f651c0-fcd5-4271-9452-b6ac41cd33cc
ms.date: 04/16/2018
ms.keywords: "*PTOKEN_STATISTICS, PTOKEN_STATISTICS, PTOKEN_STATISTICS structure pointer [Installable File System Drivers], TOKEN_STATISTICS, TOKEN_STATISTICS structure [Installable File System Drivers], _TOKEN_STATISTICS, ifsk.token_statistics, ntifs/PTOKEN_STATISTICS, ntifs/TOKEN_STATISTICS, securitystructures_5934a44f-c54e-44fe-a1c8-50b656b2b1f5.xml"
ms.topic: struct
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
- TOKEN_STATISTICS
product:
- Windows
targetos: Windows
req.typenames: TOKEN_STATISTICS, *PTOKEN_STATISTICS
---

# _TOKEN_STATISTICS structure


## -description


TOKEN_STATISTICS contains information about an access token. A driver can retrieve this information by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>. 


## -struct-fields




### -field TokenId

Specifies a locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>) that identifies this instance of the token object. 


### -field AuthenticationId

Specifies an LUID assigned to the session this token represents. There can be many tokens representing a single logon session. 


### -field ExpirationTime

Specifies the time at which this token expires. Expiration times for access tokens are not currently supported. 


### -field TokenType

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a> enumerated type indicating whether the token is a primary or impersonation token. 


### -field ImpersonationLevel

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a> enumerated type indicating the impersonation level of the token. This member is valid only if the <b>TokenType</b> is TokenImpersonation. 


### -field DynamicCharged

Specifies the amount, in bytes, of memory allocated for storing a default access-control list (DACL) and primary group identifier. 


### -field DynamicAvailable

Specifies the portion of the memory allocated for storing a DACL and primary group identifier that is not already in use. This value is returned as a count of free bytes. 


### -field GroupCount

Specifies the number of supplemental group security identifiers (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid">SID</a>) included in the token. 


### -field PrivilegeCount

Specifies the number of privileges included in the token. 


### -field ModifiedId

Specifies an LUID that changes each time the token is modified. An application can use this value as a test of whether a security context has changed since it was last used. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

