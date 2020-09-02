---
UID: NS:ndiswwan._NDIS_WWAN_SET_PACKET_SERVICE
title: _NDIS_WWAN_SET_PACKET_SERVICE (ndiswwan.h)
description: The NDIS_WWAN_SET_PACKET_SERVICE structure represents the packet service state of the MB device.
old-location: netvista\ndis_wwan_set_packet_service.htm
tech.root: netvista
ms.assetid: bded1e89-3bb5-4241-ab44-875012bfad3a
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_SET_PACKET_SERVICE structure"]
ms.keywords: "*PNDIS_WWAN_SET_PACKET_SERVICE, NDIS_WWAN_SET_PACKET_SERVICE, NDIS_WWAN_SET_PACKET_SERVICE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_PACKET_SERVICE, PNDIS_WWAN_SET_PACKET_SERVICE structure pointer [Network Drivers Starting with Windows Vista], WwanRef_b98b2778-6d41-426f-85c3-99add8477050.xml, _NDIS_WWAN_SET_PACKET_SERVICE, ndiswwan/NDIS_WWAN_SET_PACKET_SERVICE, ndiswwan/PNDIS_WWAN_SET_PACKET_SERVICE, netvista.ndis_wwan_set_packet_service"
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
req.typenames: NDIS_WWAN_SET_PACKET_SERVICE, *PNDIS_WWAN_SET_PACKET_SERVICE
f1_keywords:
 - _NDIS_WWAN_SET_PACKET_SERVICE
 - ndiswwan/_NDIS_WWAN_SET_PACKET_SERVICE
 - PNDIS_WWAN_SET_PACKET_SERVICE
 - ndiswwan/PNDIS_WWAN_SET_PACKET_SERVICE
 - NDIS_WWAN_SET_PACKET_SERVICE
 - ndiswwan/NDIS_WWAN_SET_PACKET_SERVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_SET_PACKET_SERVICE
---

# _NDIS_WWAN_SET_PACKET_SERVICE structure


## -description

The NDIS_WWAN_SET_PACKET_SERVICE structure represents the packet service state of the MB
  device.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_PACKET_SERVICE
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
NDIS_WWAN_SET_PACKET_SERVICE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_PACKET_SERVICE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field PacketServiceAction

A value from the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_packet_service_action">
     WWAN_PACKET_SERVICE_ACTION</a> enumeration that represents the packet service action to take.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_packet_service_action">WWAN_PACKET_SERVICE_ACTION</a>

