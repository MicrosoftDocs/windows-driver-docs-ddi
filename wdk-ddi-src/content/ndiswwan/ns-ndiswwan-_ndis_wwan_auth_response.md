---
UID: NS:ndiswwan._NDIS_WWAN_AUTH_RESPONSE
title: "_NDIS_WWAN_AUTH_RESPONSE"
author: windows-driver-content
description: The NDIS_WWAN_AUTH_RESPONSE structure represents a response from one of the authentication methods.
old-location: netvista\ndis_wwan_auth_response.htm
old-project: netvista
ms.assetid: 9F991E80-5155-45CE-9547-7354EE7EC4DB
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_WWAN_AUTH_RESPONSE, NDIS_WWAN_AUTH_RESPONSE, NDIS_WWAN_AUTH_RESPONSE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_AUTH_RESPONSE, PNDIS_WWAN_AUTH_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_AUTH_RESPONSE, ndiswwan/NDIS_WWAN_AUTH_RESPONSE, ndiswwan/PNDIS_WWAN_AUTH_RESPONSE, netvista.ndis_wwan_auth_response"
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
-	NDIS_WWAN_AUTH_RESPONSE
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_AUTH_RESPONSE, *PNDIS_WWAN_AUTH_RESPONSE
---

# _NDIS_WWAN_AUTH_RESPONSE structure


## -description


The NDIS_WWAN_AUTH_RESPONSE structure represents a response from one of the authentication methods.


## -syntax


````
typedef struct _NDIS_WWAN_AUTH_RESPONSE {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_AUTH_RESPONSE AuthResponse;
} NDIS_WWAN_AUTH_RESPONSE, *PNDIS_WWAN_AUTH_RESPONSE;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_AUTH_RESPONSE structure. The
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
NDIS_WWAN_AUTH_RESPONSE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_AUTH_RESPONSE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the response received for authentication challenge operation. The miniport driver returns one of the following WWAN_STATUS values as appropriate.

<table>
<tr>
<th>WWAN_STATUS_VALUE</th>
<th>Description</th>
</tr>
<tr>
<td>
WWAN_STATUS_AUTH_INCORRECT_AUTN

</td>
<td>
If the transmitted challenge has an incorrect AUTN,  the response for the AKA and AKA' challenges will have this error code. This value applies only to the AKA and AKA' authentication methods. 

</td>
</tr>
<tr>
<td>
WWAN_STATUS_AUTH_SYNC_FAILURE

</td>
<td>
 If the transmitted challenge has a synchronization failure, the response for the AKA and AKA' challenges will have this error code and will have AUTS. This value applies only to the AKA and AKA' authentication methods.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_AUTH_AMF_NOT_SET

</td>
<td>
 If the transmitted challenge is not computed with the AMF separation bit set to 1, the response for AKA' should have this error code. This value applies only to the AKA' authentication method.

</td>
</tr>
</table>
 


### -field AuthResponse

A formatted <a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a> object that represents the challenge posed by one of the authentication methods. This member (within WWAN_AUTH_RESPONSE) should be set even when <b>uStatus</b> is other than WWAN_STATUS_SUCCESS.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439821">NDIS_STATUS_WWAN_AUTH_RESPONSE</a> NDIS status notification uses this structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439821">NDIS_STATUS_WWAN_AUTH_RESPONSE</a>



<a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a>



 

 


