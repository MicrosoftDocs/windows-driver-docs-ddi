---
UID: NS:ntifs._TOKEN_PRIMARY_GROUP
title: _TOKEN_PRIMARY_GROUP
author: windows-driver-content
description: TOKEN_PRIMARY_GROUP specifies a group security identifier (SID) for an access token.
old-location: ifsk\token_primary_group.htm
old-project: ifsk
ms.assetid: 9c9a7f63-7fe8-48a9-b4d0-10586e6b86bc
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _TOKEN_PRIMARY_GROUP, TOKEN_PRIMARY_GROUP, *PTOKEN_PRIMARY_GROUP
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
req.alt-api: TOKEN_PRIMARY_GROUP
req.alt-loc: ntifs.h
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
req.typenames: TOKEN_PRIMARY_GROUP, *PTOKEN_PRIMARY_GROUP
---

# _TOKEN_PRIMARY_GROUP structure



## -description
TOKEN_PRIMARY_GROUP specifies a group security identifier (SID) for an access token. 



## -syntax

````
typedef struct _TOKEN_PRIMARY_GROUP {
  PSID PrimaryGroup;
} TOKEN_PRIMARY_GROUP, *PTOKEN_PRIMARY_GROUP;
````


## -struct-fields

### -field PrimaryGroup

Pointer to a SID structure representing a group that will become the primary group of any objects created by a process using this access token. The SID must be one of the group SIDs already in the token. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
<dt>
<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_PRIMARY_GROUP structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

