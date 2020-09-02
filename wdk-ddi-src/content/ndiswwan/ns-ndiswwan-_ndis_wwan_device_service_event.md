---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_EVENT
title: _NDIS_WWAN_DEVICE_SERVICE_EVENT (ndiswwan.h)
description: The NDIS_WWAN_DEVICE_SERVICE_EVENT structure describes unsolicited device service data that were not initiated by commands from Windows.
old-location: netvista\ndis_wwan_device_service_event.htm
tech.root: netvista
ms.assetid: 43205AA6-2B1A-4D04-9AF8-E0EB53253F5B
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_DEVICE_SERVICE_EVENT structure"]
ms.keywords: "*PNDIS_WWAN_DEVICE_SERVICE_EVENT, NDIS_WWAN_DEVICE_SERVICE_EVENT, NDIS_WWAN_DEVICE_SERVICE_EVENT structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_SERVICE_EVENT, PNDIS_WWAN_DEVICE_SERVICE_EVENT structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_EVENT, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_EVENT, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_EVENT, netvista.ndis_wwan_device_service_event"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
req.typenames: NDIS_WWAN_DEVICE_SERVICE_EVENT, *PNDIS_WWAN_DEVICE_SERVICE_EVENT
f1_keywords:
 - _NDIS_WWAN_DEVICE_SERVICE_EVENT
 - ndiswwan/_NDIS_WWAN_DEVICE_SERVICE_EVENT
 - PNDIS_WWAN_DEVICE_SERVICE_EVENT
 - ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_EVENT
 - NDIS_WWAN_DEVICE_SERVICE_EVENT
 - ndiswwan/NDIS_WWAN_DEVICE_SERVICE_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_DEVICE_SERVICE_EVENT
---

# _NDIS_WWAN_DEVICE_SERVICE_EVENT structure


## -description

The NDIS_WWAN_DEVICE_SERVICE_EVENT structure describes unsolicited device service data that were not initiated by commands from Windows.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_EVENT structure. The MB
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
NDIS_WWAN_DEVICE_SERVICE_EVENT_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_EVENT)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field Event

 




#### - EventData

The information from the event.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_service_event">WWAN_DEVICE_SERVICE_EVENT</a>

