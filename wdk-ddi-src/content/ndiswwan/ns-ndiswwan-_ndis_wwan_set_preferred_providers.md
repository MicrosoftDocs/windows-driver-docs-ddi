---
UID: NS:ndiswwan._NDIS_WWAN_SET_PREFERRED_PROVIDERS
title: _NDIS_WWAN_SET_PREFERRED_PROVIDERS (ndiswwan.h)
description: The NDIS_WWAN_SET_PREFERRED_PROVIDERS structure represents the list of preferred providers associated with the MB device.
old-location: netvista\ndis_wwan_set_preferred_providers.htm
tech.root: netvista
ms.assetid: 6741d440-0e17-4b2d-a642-0335d1f936cf
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_SET_PREFERRED_PROVIDERS structure"]
ms.keywords: "*PNDIS_WWAN_SET_PREFERRED_PROVIDERS, NDIS_WWAN_SET_PREFERRED_PROVIDERS, NDIS_WWAN_SET_PREFERRED_PROVIDERS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PREFERRED_PROVIDERS, PNDIS_WWAN_SET_PREFERRED_PROVIDERS structure pointer [Network Drivers Starting with Windows Vista], WwanRef_9e9b42a9-813f-4440-a112-9af4bc172d4e.xml, _NDIS_WWAN_SET_PREFERRED_PROVIDERS, ndiswwan/NDIS_WWAN_SET_PREFERRED_PROVIDERS, ndiswwan/PNDIS_WWAN_SET_PREFERRED_PROVIDERS, netvista.ndis_wwan_set_preferred_providers"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
targetos: Windows
req.typenames: NDIS_WWAN_SET_PREFERRED_PROVIDERS, *PNDIS_WWAN_SET_PREFERRED_PROVIDERS
f1_keywords:
 - _NDIS_WWAN_SET_PREFERRED_PROVIDERS
 - ndiswwan/_NDIS_WWAN_SET_PREFERRED_PROVIDERS
 - PNDIS_WWAN_SET_PREFERRED_PROVIDERS
 - ndiswwan/PNDIS_WWAN_SET_PREFERRED_PROVIDERS
 - NDIS_WWAN_SET_PREFERRED_PROVIDERS
 - ndiswwan/NDIS_WWAN_SET_PREFERRED_PROVIDERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_SET_PREFERRED_PROVIDERS
---

# _NDIS_WWAN_SET_PREFERRED_PROVIDERS structure


## -description

The NDIS_WWAN_SET_PREFERRED_PROVIDERS structure represents the list of preferred providers associated
  with the MB device.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PREFERRED_PROVIDERS
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
NDIS_WWAN_SET_PREFERRED_PROVIDERS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PREFERRED_PROVIDERS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field PreferredListHeader

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_list_header">WWAN_LIST_HEADER</a> object that represents a
     list of preferred providers to associate with the device.
     

<b>WwanDataClass</b> flags describe the preference of the specific data access technology and can be set
     to any combination within its own cellular class.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_list_header">WWAN_LIST_HEADER</a>

