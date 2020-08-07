---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_SESSION_READ
title: _NDIS_WWAN_DEVICE_SERVICE_SESSION_READ (ndiswwan.h)
description: The NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure represents device service session data that has been read by the miniport driver from the MB device.
old-location: netvista\ndis_wwan_device_service_session_read.htm
tech.root: netvista
ms.assetid: 6417E9B6-FDF9-4353-A966-1AFCB14A2735
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure"]
ms.keywords: "*PNDIS_WWAN_DEVICE_SERVICE_SESSION_READ, NDIS_WWAN_DEVICE_SERVICE_SESSION_READ, NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_SERVICE_SESSION_READ, PNDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_SESSION_READ, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_SESSION_READ, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_SESSION_READ, netvista.ndis_wwan_device_service_session_read"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_DEVICE_SERVICE_SESSION_READ"
 - "NDIS_WWAN_DEVICE_SERVICE_SESSION_READ"
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
- NDIS_WWAN_DEVICE_SERVICE_SESSION_READ
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_SERVICE_SESSION_READ, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_READ
---

# _NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure


## -description


The NDIS_WWAN_DEVICE_SERVICE_SESSION_READ structure represents device service session data that has been read by the miniport driver from the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SESSION_READ
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
NDIS_WWAN_DEVICE_SERVICE_SESSION_READ_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SESSION_READ)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field ReadData

The data that has been read from a device service session.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_service_session_read">WWAN_DEVICE_SERVICE_SESSION_READ</a>
 

 

