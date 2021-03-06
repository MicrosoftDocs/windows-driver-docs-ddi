---
UID: NS:ndiswwan._NDIS_WWAN_IP_ADDRESS_STATE
title: _NDIS_WWAN_IP_ADDRESS_STATE (ndiswwan.h)
description: The NDIS_WWAN_IP_ADDRESS_STATE structure represents the IP address of a PDP context.
old-location: netvista\ndis_wwan_ip_address_state.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_IP_ADDRESS_STATE structure"]
ms.keywords: "*PNDIS_WWAN_IP_ADDRESS_STATE, NDIS_WWAN_IP_ADDRESS_STATE, NDIS_WWAN_IP_ADDRESS_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_IP_ADDRESS_STATE, PNDIS_WWAN_IP_ADDRESS_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_IP_ADDRESS_STATE, ndiswwan/NDIS_WWAN_IP_ADDRESS_STATE, ndiswwan/PNDIS_WWAN_IP_ADDRESS_STATE, netvista.ndis_wwan_ip_address_state"
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
targetos: Windows
req.typenames: NDIS_WWAN_IP_ADDRESS_STATE, *PNDIS_WWAN_IP_ADDRESS_STATE
f1_keywords:
 - _NDIS_WWAN_IP_ADDRESS_STATE
 - ndiswwan/_NDIS_WWAN_IP_ADDRESS_STATE
 - PNDIS_WWAN_IP_ADDRESS_STATE
 - ndiswwan/PNDIS_WWAN_IP_ADDRESS_STATE
 - NDIS_WWAN_IP_ADDRESS_STATE
 - ndiswwan/NDIS_WWAN_IP_ADDRESS_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_IP_ADDRESS_STATE
 - PNDIS_WWAN_IP_ADDRESS_STATE
 - NDIS_WWAN_IP_ADDRESS_STATE
---

# _NDIS_WWAN_IP_ADDRESS_STATE structure


## -description

The NDIS_WWAN_IP_ADDRESS_STATE structure represents the IP address of a PDP context.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_IP_ADDRESS_STATE structure. The MB
     Service sets the header with the values that are shown in the following table when it sends the data
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
NDIS_WWAN_IP_ADDRESS_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_IP_ADDRESS_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field WwanIpAddressState

The PDP context's IP address.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_ip_address_state">WWAN_IP_ADDRESS_STATE</a>

