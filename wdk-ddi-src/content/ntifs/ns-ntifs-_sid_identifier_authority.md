---
UID: NS:ntifs._SID_IDENTIFIER_AUTHORITY
title: _SID_IDENTIFIER_AUTHORITY
author: windows-driver-content
description: The SID_IDENTIFIER_AUTHORITY structure represents the top-level authority of a security identifier (SID).
old-location: ifsk\sid_identifier_authority.htm
old-project: ifsk
ms.assetid: 66d8b02d-fbab-4ff7-8f47-858b9f143171
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _SID_IDENTIFIER_AUTHORITY, SID_IDENTIFIER_AUTHORITY, *PSID_IDENTIFIER_AUTHORITY
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
req.alt-api: SID_IDENTIFIER_AUTHORITY
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
req.typenames: SID_IDENTIFIER_AUTHORITY, *PSID_IDENTIFIER_AUTHORITY
---

# _SID_IDENTIFIER_AUTHORITY structure



## -description
The SID_IDENTIFIER_AUTHORITY structure represents the top-level authority of a security identifier (SID). 



## -syntax

````
typedef struct _SID_IDENTIFIER_AUTHORITY {
  UCHAR Value[6];
} SID_IDENTIFIER_AUTHORITY, *PSID_IDENTIFIER_AUTHORITY;
````


## -struct-fields

### -field Value

An array of six bytes specifying a SID's top-level authority. 


## -remarks
The identifier authority value identifies the agency that issued the SID. The following identifier authorities are predefined. 

SECURITY_NULL_SID_AUTHORITY

0

SECURITY_WORLD_SID_AUTHORITY

1

SECURITY_LOCAL_SID_AUTHORITY

2

SECURITY_CREATOR_SID_AUTHORITY

3

SECURITY_NON_UNIQUE_AUTHORITY

4

SECURITY_NT_AUTHORITY

5


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SID_IDENTIFIER_AUTHORITY structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

