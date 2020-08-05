---
UID: NS:ndiswwan._NDIS_WWAN_SET_DEVICE_RESET
title: _NDIS_WWAN_SET_DEVICE_RESET (ndiswwan.h)
description: The NDIS_WWAN_SET_DEVICE_RESET structure represents a command to reset a modem device. It is sent as part of an OID_WWAN_DEVICE_RESET set request.
old-location: netvista\ndis_wwan_set_device_reset.htm
tech.root: netvista
ms.assetid: 73894308-CFE0-49EF-BB09-E104CEE9C746
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_SET_DEVICE_RESET structure"]
ms.keywords: "*PNDIS_WWAN_SET_DEVICE_RESET, NDIS_WWAN_SET_DEVICE_RESET, NDIS_WWAN_SET_DEVICE_RESET structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_DEVICE_RESET, PNDIS_WWAN_SET_DEVICE_RESET structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SET_DEVICE_RESET, ndiswwan/NDIS_WWAN_SET_DEVICE_RESET, ndiswwan/PNDIS_WWAN_SET_DEVICE_RESET, netvista.ndis_wwan_set_device_reset"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SET_DEVICE_RESET"
 - "NDIS_WWAN_SET_DEVICE_RESET"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
- NDIS_WWAN_SET_DEVICE_RESET
targetos: Windows
req.typenames: NDIS_WWAN_SET_DEVICE_RESET, *PNDIS_WWAN_SET_DEVICE_RESET
---

# _NDIS_WWAN_SET_DEVICE_RESET structure


## -description


The <b>NDIS_WWAN_SET_DEVICE_RESET</b> structure represents a command to reset a modem device. It is sent as part of an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-reset">OID_WWAN_DEVICE_RESET</a> set request.


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_SET_DEVICE_RESET</b> structure.
     The MB Service sets the header with the values that are shown in the following table when it sends the
     data structure to the miniport driver for 
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
NDIS_WWAN_SET_DEVICE_RESET_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_DEVICE_RESET)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-modem-reset-operations">MB modem reset operations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-device-reset">OID_WWAN_DEVICE_RESET</a>
 

 

