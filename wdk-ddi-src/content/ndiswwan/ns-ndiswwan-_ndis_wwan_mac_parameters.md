---
UID: NS:ndiswwan._NDIS_WWAN_MAC_PARAMETERS
title: _NDIS_WWAN_MAC_PARAMETERS (ndiswwan.h)
description: The NDIS_WWAN_MAC_PARAMETERS structure is used by OID_WWAN_CREATE_MAC when processing a request to create an NDIS port for a new PDP context.
old-location: netvista\ndis_wwan_mac_parameters.htm
tech.root: netvista
ms.assetid: 661DA853-E848-4FEB-995F-EC5F20CE36EB
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_MAC_PARAMETERS, NDIS_WWAN_MAC_PARAMETERS, NDIS_WWAN_MAC_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_MAC_PARAMETERS, PNDIS_WWAN_MAC_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_MAC_PARAMETERS, ndiswwan/NDIS_WWAN_MAC_PARAMETERS, ndiswwan/PNDIS_WWAN_MAC_PARAMETERS, netvista.ndis_wwan_mac_parameters"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.1 and later versions of Windows.
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
-	ndiswwan.h
api_name:
-	NDIS_WWAN_MAC_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_MAC_PARAMETERS, *PNDIS_WWAN_MAC_PARAMETERS
---

# _NDIS_WWAN_MAC_PARAMETERS structure


## -description


The NDIS_WWAN_MAC_PARAMETERS structure is used by <a href="https://msdn.microsoft.com/library/windows/hardware/dn449750">OID_WWAN_CREATE_MAC</a> when processing a request to create an NDIS port for a new PDP context.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_MAC_PARAMETERS structure.

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
NDIS_WWAN_MAC_PARAMETERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_MAC_PARAMETERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn449750">OID_WWAN_CREATE_MAC</a>
 

 

