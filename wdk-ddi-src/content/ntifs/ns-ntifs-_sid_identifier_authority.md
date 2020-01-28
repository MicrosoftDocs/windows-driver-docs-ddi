---
UID: NS:ntifs._SID_IDENTIFIER_AUTHORITY
title: _SID_IDENTIFIER_AUTHORITY (ntifs.h)
description: The SID_IDENTIFIER_AUTHORITY structure represents the top-level authority of a security identifier (SID).
old-location: ifsk\sid_identifier_authority.htm
tech.root: ifsk
ms.assetid: 66d8b02d-fbab-4ff7-8f47-858b9f143171
ms.date: 04/16/2018
ms.keywords: "*PSID_IDENTIFIER_AUTHORITY, PSID_IDENTIFIER_AUTHORITY, PSID_IDENTIFIER_AUTHORITY structure pointer [Installable File System Drivers], SID_IDENTIFIER_AUTHORITY, SID_IDENTIFIER_AUTHORITY structure [Installable File System Drivers], _SID_IDENTIFIER_AUTHORITY, ifsk.sid_identifier_authority, ntifs/PSID_IDENTIFIER_AUTHORITY, ntifs/SID_IDENTIFIER_AUTHORITY, securitystructures_d1535875-a778-4b95-b736-e357e5379c19.xml"
f1_keywords:
 - "ntifs/SID_IDENTIFIER_AUTHORITY"
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
- SID_IDENTIFIER_AUTHORITY
product:
- Windows
targetos: Windows
req.typenames: SID_IDENTIFIER_AUTHORITY, *PSID_IDENTIFIER_AUTHORITY
---

# _SID_IDENTIFIER_AUTHORITY structure


## -description


The SID_IDENTIFIER_AUTHORITY structure represents the top-level authority of a security identifier (SID). 


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlinitializesid">RtlInitializeSid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>
 

 

