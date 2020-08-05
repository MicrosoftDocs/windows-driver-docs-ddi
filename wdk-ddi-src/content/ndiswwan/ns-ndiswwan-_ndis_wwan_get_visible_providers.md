---
UID: NS:ndiswwan._NDIS_WWAN_GET_VISIBLE_PROVIDERS
title: _NDIS_WWAN_GET_VISIBLE_PROVIDERS (ndiswwan.h)
description: The NDIS_WWAN_GET_VISIBLE_PROVIDERS structure is used to request the miniport driver get either all visible providers or only multi-carrier visible providers.
old-location: netvista\ndis_wwan_get_visible_providers.htm
tech.root: netvista
ms.assetid: C1AF383A-2D9D-4B2F-A925-D138E1B7AA4F
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_GET_VISIBLE_PROVIDERS structure"]
ms.keywords: "*PNDIS_WWAN_GET_VISIBLE_PROVIDERS, NDIS_WWAN_GET_VISIBLE_PROVIDERS, NDIS_WWAN_GET_VISIBLE_PROVIDERS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_GET_VISIBLE_PROVIDERS, PNDIS_WWAN_GET_VISIBLE_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_GET_VISIBLE_PROVIDERS, ndiswwan/NDIS_WWAN_GET_VISIBLE_PROVIDERS, ndiswwan/PNDIS_WWAN_GET_VISIBLE_PROVIDERS, netvista.ndis_wwan_get_visible_providers"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_GET_VISIBLE_PROVIDERS"
 - "NDIS_WWAN_GET_VISIBLE_PROVIDERS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndiswwan.h
api_name:
- NDIS_WWAN_GET_VISIBLE_PROVIDERS
targetos: Windows
req.typenames: NDIS_WWAN_GET_VISIBLE_PROVIDERS, *PNDIS_WWAN_GET_VISIBLE_PROVIDERS
---

# _NDIS_WWAN_GET_VISIBLE_PROVIDERS structure


## -description


The NDIS_WWAN_GET_VISIBLE_PROVIDERS structure is used to request the miniport driver get either all visible providers or only multi-carrier visible providers.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_GET_VISIBLE_PROVIDERS
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
NDIS_WWAN_GET_VISIBLE_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_GET_VISIBLE_PROVIDERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field VisibleProviders

A formatted WWAN_GET_VISIBLE_PROVIDERS object that provides additional information to the miniport about the type of providers to return.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_get_visible_providers">WWAN_GET_VISIBLE_PROVIDERS</a>
 

 

