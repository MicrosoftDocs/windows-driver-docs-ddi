---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SET_SERVICE_SESSION
title: _NDIS_WWAN_DEVICE_SET_SERVICE_SESSION (ndiswwan.h)
description: The NDIS_WWAN_SET_DEVICE_SERVICE_SESSION structure represents a session state operation to be performed on a device service.
old-location: netvista\ndis_wwan_set_device_service_session.htm
tech.root: netvista
ms.assetid: D68B2071-D32B-4A6A-ACB8-001865CABD92
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SET_DEVICE_SERVICE_SESSION, NDIS_WWAN_SET_DEVICE_SERVICE_SESSION, NDIS_WWAN_SET_DEVICE_SERVICE_SESSION structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_DEVICE_SERVICE_SESSION, PNDIS_WWAN_SET_DEVICE_SERVICE_SESSION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SET_SERVICE_SESSION, ndiswwan/NDIS_WWAN_SET_DEVICE_SERVICE_SESSION, ndiswwan/PNDIS_WWAN_SET_DEVICE_SERVICE_SESSION, netvista.ndis_wwan_set_device_service_session"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SET_DEVICE_SERVICE_SESSION"
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
- NDIS_WWAN_SET_DEVICE_SERVICE_SESSION
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_DEVICE_SERVICE_SESSION, *PNDIS_WWAN_SET_DEVICE_SERVICE_SESSION
---

# _NDIS_WWAN_DEVICE_SET_SERVICE_SESSION structure


## -description


The NDIS_WWAN_SET_DEVICE_SERVICE_SESSION structure represents a session state operation to be performed on a device service.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_DEVICE_SERVICE_SESSION
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
NDIS_WWAN_SET_DEVICE_SERVICE_SESSION_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_DEVICE_SERVICE_SESSION)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field Session

The requested session state set operation.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_service_session">WWAN_DEVICE_SERVICE_SESSION</a>
 

 

