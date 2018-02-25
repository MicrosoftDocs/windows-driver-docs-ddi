---
UID: NS:ntifs._TOKEN_GROUPS_AND_PRIVILEGES
title: "_TOKEN_GROUPS_AND_PRIVILEGES"
author: windows-driver-content
description: TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.
old-location: ifsk\token_groups_and_privileges.htm
old-project: ifsk
ms.assetid: 27d4793d-bdb4-46c5-b6e4-a2136e899adc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PTOKEN_GROUPS_AND_PRIVILEGES, ,, A, D, E, G, I, K, L, N, O, P, PTOKEN_GROUPS_AND_PRIVILEGES, PTOKEN_GROUPS_AND_PRIVILEGES structure pointer [Installable File System Drivers], R, S, T, TOKEN_GROUPS_AND_PRIVILEGES, TOKEN_GROUPS_AND_PRIVILEGES structure [Installable File System Drivers], U, V, _, _TOKEN_GROUPS_AND_PRIVILEGES, ifsk.token_groups_and_privileges, ntifs/PTOKEN_GROUPS_AND_PRIVILEGES, ntifs/TOKEN_GROUPS_AND_PRIVILEGES, securitystructures_4cab5ceb-66b1-4445-a9b0-a428fc628ab5.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	TOKEN_GROUPS_AND_PRIVILEGES
product: Windows
targetos: Windows
req.typenames: TOKEN_GROUPS_AND_PRIVILEGES, *PTOKEN_GROUPS_AND_PRIVILEGES
---

# _TOKEN_GROUPS_AND_PRIVILEGES structure


## -description


TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.


## -syntax


````
typedef struct _TOKEN_GROUPS_AND_PRIVILEGES {
  ULONG                SidCount;
  ULONG                SidLength;
  PSID_AND_ATTRIBUTES  Sids;
  ULONG                RestrictedSidCount;
  ULONG                RestrictedSidLength;
  PSID_AND_ATTRIBUTES  RestrictedSids;
  ULONG                PrivilegeCount;
  ULONG                PrivilegeLength;
  PLUID_AND_ATTRIBUTES Privileges;
  LUID                 AuthenticationId;
} TOKEN_GROUPS_AND_PRIVILEGES, *PTOKEN_GROUPS_AND_PRIVILEGES;
````


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

A pointer to <a href="..\ntifs\ns-ntifs-_sid_and_attributes.md">SID_AND_ATTRIBUTES</a> structures that contain a set of restricted SIDs and corresponding attributes. 


### -field PrivilegeCount

Specifies the number of privileges included in the access token. 


### -field PrivilegeLength

Specifies the length, in bytes, needed to hold all of the privileges. 


### -field Privileges

A pointer to <a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a> structures that contain a set of privileges. 


### -field AuthenticationId

The locally unique identifier (LUID) of the authenticator of the token. 


## -see-also

<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>



<a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a>



<a href="..\ntifs\ns-ntifs-_token_statistics.md">TOKEN_STATISTICS</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>



<a href="..\ntifs\ns-ntifs-_sid_and_attributes.md">SID_AND_ATTRIBUTES</a>



<a href="..\ntifs\ns-ntifs-_token_privileges.md">TOKEN_PRIVILEGES</a>



<a href="..\ntifs\ns-ntifs-_token_primary_group.md">TOKEN_PRIMARY_GROUP</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\ntifs\ns-ntifs-_token_owner.md">TOKEN_OWNER</a>



<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>



<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\ntifs\ns-ntifs-_token_user.md">TOKEN_USER</a>



<a href="..\ntifs\ns-ntifs-_token_default_dacl.md">TOKEN_DEFAULT_DACL</a>



<a href="..\ntifs\ns-ntifs-_token_source.md">TOKEN_SOURCE</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="..\ntifs\ne-ntifs-_token_type.md">TOKEN_TYPE</a>



<a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_GROUPS_AND_PRIVILEGES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

