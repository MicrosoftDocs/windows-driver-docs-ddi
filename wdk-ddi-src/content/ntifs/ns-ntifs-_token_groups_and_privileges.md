---
UID: NS:ntifs._TOKEN_GROUPS_AND_PRIVILEGES
title: "_TOKEN_GROUPS_AND_PRIVILEGES" (ntifs.h)
description: TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.
old-location: ifsk\token_groups_and_privileges.htm
tech.root: ifsk
ms.assetid: 27d4793d-bdb4-46c5-b6e4-a2136e899adc
ms.date: 04/16/2018
ms.keywords: "*PTOKEN_GROUPS_AND_PRIVILEGES, PTOKEN_GROUPS_AND_PRIVILEGES, PTOKEN_GROUPS_AND_PRIVILEGES structure pointer [Installable File System Drivers], TOKEN_GROUPS_AND_PRIVILEGES, TOKEN_GROUPS_AND_PRIVILEGES structure [Installable File System Drivers], _TOKEN_GROUPS_AND_PRIVILEGES, ifsk.token_groups_and_privileges, ntifs/PTOKEN_GROUPS_AND_PRIVILEGES, ntifs/TOKEN_GROUPS_AND_PRIVILEGES, securitystructures_4cab5ceb-66b1-4445-a9b0-a428fc628ab5.xml"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	TOKEN_GROUPS_AND_PRIVILEGES
product:
- Windows
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

A pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a> structures that contain a set of restricted SIDs and corresponding attributes. 


### -field PrivilegeCount

Specifies the number of privileges included in the access token. 


### -field PrivilegeLength

Specifies the length, in bytes, needed to hold all of the privileges. 


### -field Privileges

A pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549716">LUID_AND_ATTRIBUTES</a> structures that contain a set of privileges. 


### -field AuthenticationId

The locally unique identifier (LUID) of the authenticator of the token. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549716">LUID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556724">SeTokenIsRestricted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556831">TOKEN_DEFAULT_DACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556838">TOKEN_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556842">TOKEN_OWNER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556845">TOKEN_PRIMARY_GROUP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556846">TOKEN_PRIVILEGES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556848">TOKEN_SOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556849">TOKEN_STATISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556851">TOKEN_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556855">TOKEN_USER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
 

 

