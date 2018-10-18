---
UID: NS:ndiswwan._NDIS_WWAN_SET_PRESHUTDOWN_STATE
title: "_NDIS_WWAN_SET_PRESHUTDOWN_STATE"
author: windows-driver-content
description: The NDIS_WWAN_SET_PRESHUTDOWN_STATE structure represents the command to notify the modem to finish all operations and prepare to shut down.
old-location: netvista\ndis_wwan_set_preshutdown_state.htm
tech.root: netvista
ms.assetid: B1DC847C-B596-452D-B96E-3B78C6F995B2
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SET_PRESHUTDOWN_STATE, NDIS_WWAN_SET_PRESHUTDOWN_STATE, NDIS_WWAN_SET_PRESHUTDOWN_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PRESHUTDOWN_STATE, PNDIS_WWAN_SET_PRESHUTDOWN_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_PRESHUTDOWN_STATE, ndiswwan/NDIS_WWAN_SET_PRESHUTDOWN_STATE, ndiswwan/PNDIS_WWAN_SET_PRESHUTDOWN_STATE, netvista.ndis_wwan_set_preshutdown_state"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 10, version 1511.
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
-	NDIS_WWAN_SET_PRESHUTDOWN_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_PRESHUTDOWN_STATE, *PNDIS_WWAN_SET_PRESHUTDOWN_STATE
---

# _NDIS_WWAN_SET_PRESHUTDOWN_STATE structure


## -description


The NDIS_WWAN_SET_PRESHUTDOWN_STATE structure represents the command to notify the modem to finish all operations and prepare to shut down.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PRESHUTDOWN_STATE
     structure. 

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
 NDIS_WWAN_SET_PRESHUTDOWN_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PRESHUTDOWN_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt593239">OID_WWAN_PRESHUTDOWN</a>
 

 

