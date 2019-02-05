---
UID: NS:ndiswwan._NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS
title: _NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS (ndiswwan.h)
description: The NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure represents a list of preferred multicarrier providers associated with the MB device.
old-location: netvista\ndis_wwan_set_preferred_multicarrier_providers.htm
tech.root: netvista
ms.assetid: D57068D9-D671-4E56-ABD0-CD91BD91404D
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, ndiswwan/NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, ndiswwan/PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, netvista.ndis_wwan_set_preferred_multicarrier_providers"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS, *PNDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS
---

# _NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure


## -description


The NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS structure represents a list of preferred multicarrier providers associated with the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
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
NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PREFERRED_MULTICARRIER_PROVIDERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field PreferredListHeader

A formatted 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a> object that represents a
     list of preferred multicarrier providers to associate with the MB device.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a>
 

 

