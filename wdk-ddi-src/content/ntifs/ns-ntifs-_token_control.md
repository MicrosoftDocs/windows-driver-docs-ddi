---
UID: NS:ntifs._TOKEN_CONTROL
title: "_TOKEN_CONTROL"
author: windows-driver-content
description: The TOKEN_CONTROL structure contains information that identifies an access token.
old-location: ifsk\token_control.htm
old-project: ifsk
ms.assetid: 3e0d41f4-4918-4768-a341-25d27f0a8af0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_CONTROL, PTOKEN_CONTROL, PTOKEN_CONTROL structure pointer [Installable File System Drivers], TOKEN_CONTROL, TOKEN_CONTROL structure [Installable File System Drivers], _TOKEN_CONTROL, ifsk.token_control, ntifs/PTOKEN_CONTROL, ntifs/TOKEN_CONTROL, securitystructures_26958d39-4a12-4979-b0cc-7a880e3d2384.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	TOKEN_CONTROL
product: Windows
targetos: Windows
req.typenames: TOKEN_CONTROL, *PTOKEN_CONTROL
---

# _TOKEN_CONTROL structure


## -description


The TOKEN_CONTROL structure contains information that identifies an access token.


## -syntax


````
typedef struct _TOKEN_CONTROL {
  LUID         TokenId;
  LUID         AuthenticationId;
  LUID         ModifiedId;
  TOKEN_SOURCE TokenSource;
} TOKEN_CONTROL, *PTOKEN_CONTROL;
````


## -struct-fields




### -field TokenId

Specifies a locally unique identifier (LUID) identifying this instance of the token object. 


### -field AuthenticationId

Specifies an LUID assigned to the session this token represents. There can be many tokens representing a single logon session. 


### -field ModifiedId

Specifies an LUID that changes each time the token is modified. An application can use this value as a test of whether a security context has changed since it was last used. 


### -field TokenSource

Specifies a <a href="..\ntifs\ns-ntifs-_token_source.md">TOKEN_SOURCE</a> structure identifying the source that issued the token. This information is used in audit logging. 


## -see-also

<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a>



<a href="..\ntifs\ns-ntifs-_token_source.md">TOKEN_SOURCE</a>



<a href="..\ntifs\ns-ntifs-_token_statistics.md">TOKEN_STATISTICS</a>



<a href="..\ntifs\ns-ntifs-_token_default_dacl.md">TOKEN_DEFAULT_DACL</a>



<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



<a href="..\ntifs\ne-ntifs-_token_type.md">TOKEN_TYPE</a>



<a href="..\ntifs\ns-ntifs-_token_privileges.md">TOKEN_PRIVILEGES</a>



<a href="..\ntifs\ns-ntifs-_token_owner.md">TOKEN_OWNER</a>



<a href="..\ntifs\ns-ntifs-_token_primary_group.md">TOKEN_PRIMARY_GROUP</a>



<a href="..\ntifs\ns-ntifs-_token_user.md">TOKEN_USER</a>



<a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_CONTROL structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

