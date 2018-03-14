---
UID: NS:ndiswwan._NDIS_WWAN_AUTH_CHALLENGE
title: "_NDIS_WWAN_AUTH_CHALLENGE"
author: windows-driver-content
description: The NDIS_WWAN_AUTH_CHALLENGE structure represents an authentication challenge used by one of the authentication methods.
old-location: netvista\ndis_wwan_auth_challenge.htm
old-project: netvista
ms.assetid: 7C5CE666-D8C9-4A01-A38E-612B69E3A5FB
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_WWAN_AUTH_CHALLENGE, NDIS_WWAN_AUTH_CHALLENGE, NDIS_WWAN_AUTH_CHALLENGE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_AUTH_CHALLENGE, PNDIS_WWAN_AUTH_CHALLENGE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_AUTH_CHALLENGE, ndiswwan/NDIS_WWAN_AUTH_CHALLENGE, ndiswwan/PNDIS_WWAN_AUTH_CHALLENGE, netvista.ndis_wwan_auth_challenge"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_AUTH_CHALLENGE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_AUTH_CHALLENGE, *PNDIS_WWAN_AUTH_CHALLENGE
---

# _NDIS_WWAN_AUTH_CHALLENGE structure


## -description


The NDIS_WWAN_AUTH_CHALLENGE structure represents an authentication challenge used by one of the authentication methods.


## -syntax


````
typedef struct _NDIS_WWAN_AUTH_CHALLENGE {
  NDIS_OBJECT_HEADER  Header;
  WWAN_AUTH_CHALLENGE AuthChallenge;
} NDIS_WWAN_AUTH_CHALLENGE, *PNDIS_WWAN_AUTH_CHALLENGE;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_AUTH_CHALLENGE structure. The
     MB service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_AUTH_CHALLENGE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_AUTH_CHALLENGE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field AuthChallenge

A formatted <a href="..\wwan\ns-wwan-_wwan_auth_challenge.md">WWAN_AUTH_CHALLENGE</a> object that represents the challenge posed by one of the authentication methods.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_auth_challenge.md">WWAN_AUTH_CHALLENGE</a>



 

 


