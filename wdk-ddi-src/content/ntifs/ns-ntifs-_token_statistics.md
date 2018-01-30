---
UID: NS:ntifs._TOKEN_STATISTICS
title: "_TOKEN_STATISTICS"
author: windows-driver-content
description: TOKEN_STATISTICS contains information about an access token. A driver can retrieve this information by calling SeQueryInformationToken or ZwQueryInformationToken.
old-location: ifsk\token_statistics.htm
old-project: ifsk
ms.assetid: a7f651c0-fcd5-4271-9452-b6ac41cd33cc
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: TOKEN_STATISTICS, PTOKEN_STATISTICS structure pointer [Installable File System Drivers], securitystructures_5934a44f-c54e-44fe-a1c8-50b656b2b1f5.xml, TOKEN_STATISTICS structure [Installable File System Drivers], ntifs/PTOKEN_STATISTICS, PTOKEN_STATISTICS, _TOKEN_STATISTICS, ifsk.token_statistics, ntifs/TOKEN_STATISTICS, *PTOKEN_STATISTICS
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
-	TOKEN_STATISTICS
product: Windows
targetos: Windows
req.typenames: TOKEN_STATISTICS, *PTOKEN_STATISTICS
---

# _TOKEN_STATISTICS structure


## -description


TOKEN_STATISTICS contains information about an access token. A driver can retrieve this information by calling <a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a> or <a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>. 


## -syntax


````
typedef struct _TOKEN_STATISTICS {
  LUID                         TokenId;
  LUID                         AuthenticationId;
  LARGE_INTEGER                ExpirationTime;
  TOKEN_TYPE                   TokenType;
  SECURITY_IMPERSONATION_LEVEL ImpersonationLevel;
  ULONG                        DynamicCharged;
  ULONG                        DynamicAvailable;
  ULONG                        GroupCount;
  ULONG                        PrivilegeCount;
  LUID                         ModifiedId;
} TOKEN_STATISTICS, *PTOKEN_STATISTICS;
````


## -struct-fields




### -field TokenId

Specifies a locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) that identifies this instance of the token object. 


### -field AuthenticationId

Specifies an LUID assigned to the session this token represents. There can be many tokens representing a single logon session. 


### -field ExpirationTime

Specifies the time at which this token expires. Expiration times for access tokens are not currently supported. 


### -field TokenType

Specifies a <a href="..\ntifs\ne-ntifs-_token_type.md">TOKEN_TYPE</a> enumerated type indicating whether the token is a primary or impersonation token. 


### -field ImpersonationLevel

Specifies a <a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a> enumerated type indicating the impersonation level of the token. This member is valid only if the <b>TokenType</b> is TokenImpersonation. 


### -field DynamicCharged

Specifies the amount, in bytes, of memory allocated for storing a default access-control list (DACL) and primary group identifier. 


### -field DynamicAvailable

Specifies the portion of the memory allocated for storing a DACL and primary group identifier that is not already in use. This value is returned as a count of free bytes. 


### -field GroupCount

Specifies the number of supplemental group security identifiers (<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>) included in the token. 


### -field PrivilegeCount

Specifies the number of privileges included in the token. 


### -field ModifiedId

Specifies an LUID that changes each time the token is modified. An application can use this value as a test of whether a security context has changed since it was last used. 


## -see-also

<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>

<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

<a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>

<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>

<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>

<a href="..\ntifs\ne-ntifs-_token_type.md">TOKEN_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_STATISTICS structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

