---
UID: NE:ntifs._TOKEN_TYPE
title: _TOKEN_TYPE
author: windows-driver-content
description: The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token.
old-location: ifsk\token_type.htm
old-project: ifsk
ms.assetid: 2ad78d17-9baa-45cf-a620-01c2ccd14338
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _TOKEN_TYPE, TOKEN_TYPE, *PTOKEN_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TOKEN_TYPE
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
req.irql: PASSIVE_LEVEL
req.typenames: TOKEN_TYPE
---

# _TOKEN_TYPE enumeration



## -description
The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token. 



## -syntax

````
typedef enum _TOKEN_TYPE { 
  TokenPrimary        = 1,
  TokenImpersonation  = 2
} TOKEN_TYPE, *PTOKEN_TYPE;
````


## -enum-fields

### -field TokenPrimary

Indicates a primary token. 


### -field TokenImpersonation

Indicates an impersonation token. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>
</dt>
<dt>
<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_token_statistics.md">TOKEN_STATISTICS</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_TYPE enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

