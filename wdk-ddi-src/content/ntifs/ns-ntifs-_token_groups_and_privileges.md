---
UID: NS:ntifs._TOKEN_GROUPS_AND_PRIVILEGES
title: _TOKEN_GROUPS_AND_PRIVILEGES (ntifs.h)
description: TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.
old-location: ifsk\token_groups_and_privileges.htm
tech.root: ifsk
ms.assetid: 27d4793d-bdb4-46c5-b6e4-a2136e899adc
ms.date: 04/16/2018
keywords: ["TOKEN_GROUPS_AND_PRIVILEGES structure"]
ms.keywords: "*PTOKEN_GROUPS_AND_PRIVILEGES, PTOKEN_GROUPS_AND_PRIVILEGES, PTOKEN_GROUPS_AND_PRIVILEGES structure pointer [Installable File System Drivers], TOKEN_GROUPS_AND_PRIVILEGES, TOKEN_GROUPS_AND_PRIVILEGES structure [Installable File System Drivers], _TOKEN_GROUPS_AND_PRIVILEGES, ifsk.token_groups_and_privileges, ntifs/PTOKEN_GROUPS_AND_PRIVILEGES, ntifs/TOKEN_GROUPS_AND_PRIVILEGES, securitystructures_4cab5ceb-66b1-4445-a9b0-a428fc628ab5.xml"
f1_keywords:
 - "ntifs/TOKEN_GROUPS_AND_PRIVILEGES"
 - "TOKEN_GROUPS_AND_PRIVILEGES"
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
- TOKEN_GROUPS_AND_PRIVILEGES
targetos: Windows
req.typenames: TOKEN_GROUPS_AND_PRIVILEGES, *PTOKEN_GROUPS_AND_PRIVILEGES
---

# _TOKEN_GROUPS_AND_PRIVILEGES structure


## -description


TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.


## -struct-fields




### -field SidCount

Specifies the number of SIDs in the access token. 


### -field SidLength

Specifies the length, in bytes, required to hold all of the user SIDs and the account SID for the group. 


### -field Sids

A pointer to SID_AND_ATTRIBUTES structures that contain a set of SIDs and corresponding attributes. 


### -field RestrictedSidCount

Specifies the number of the restricted SIDs included in the access token. 


### -field RestrictedSidLength

Specifies the length, in bytes, required to hold all of the restricted SIDs. 


### -field RestrictedSids

A pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_and_attributes">SID_AND_ATTRIBUTES</a> structures that contain a set of restricted SIDs and corresponding attributes. 


### -field PrivilegeCount

Specifies the number of privileges included in the access token. 


### -field PrivilegeLength

Specifies the length, in bytes, needed to hold all of the privileges. 


### -field Privileges

A pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_luid_and_attributes">LUID_AND_ATTRIBUTES</a> structures that contain a set of privileges. 


### -field AuthenticationId

The locally unique identifier (LUID) of the authenticator of the token. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_luid_and_attributes">LUID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid_and_attributes">SID_AND_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sefiltertoken">SeFilterToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisrestricted">SeTokenIsRestricted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_default_dacl">TOKEN_DEFAULT_DACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_owner">TOKEN_OWNER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_primary_group">TOKEN_PRIMARY_GROUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_privileges">TOKEN_PRIVILEGES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_source">TOKEN_SOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_user">TOKEN_USER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

