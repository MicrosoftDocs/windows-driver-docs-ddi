---
UID: NS:ntifs._SID_IDENTIFIER_AUTHORITY
title: "_SID_IDENTIFIER_AUTHORITY"
author: windows-driver-content
description: The SID_IDENTIFIER_AUTHORITY structure represents the top-level authority of a security identifier (SID).
old-location: ifsk\sid_identifier_authority.htm
old-project: ifsk
ms.assetid: 66d8b02d-fbab-4ff7-8f47-858b9f143171
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: "_SID_IDENTIFIER_AUTHORITY, ifsk.sid_identifier_authority, ntifs/PSID_IDENTIFIER_AUTHORITY, securitystructures_d1535875-a778-4b95-b736-e357e5379c19.xml, SID_IDENTIFIER_AUTHORITY structure [Installable File System Drivers], PSID_IDENTIFIER_AUTHORITY, PSID_IDENTIFIER_AUTHORITY structure pointer [Installable File System Drivers], *PSID_IDENTIFIER_AUTHORITY, ntifs/SID_IDENTIFIER_AUTHORITY, SID_IDENTIFIER_AUTHORITY"
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
-	SID_IDENTIFIER_AUTHORITY
product: Windows
targetos: Windows
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

<table>
<tr>
<th>Identifier Authority</th>
<th>Value</th>
</tr>
<tr>
<td>
SECURITY_NULL_SID_AUTHORITY

</td>
<td>
0

</td>
</tr>
<tr>
<td>
SECURITY_WORLD_SID_AUTHORITY

</td>
<td>
1

</td>
</tr>
<tr>
<td>
SECURITY_LOCAL_SID_AUTHORITY

</td>
<td>
2

</td>
</tr>
<tr>
<td>
SECURITY_CREATOR_SID_AUTHORITY

</td>
<td>
3

</td>
</tr>
<tr>
<td>
SECURITY_NON_UNIQUE_AUTHORITY

</td>
<td>
4

</td>
</tr>
<tr>
<td>
SECURITY_NT_AUTHORITY

</td>
<td>
5

</td>
</tr>
</table>
 




## -see-also

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SID_IDENTIFIER_AUTHORITY structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

