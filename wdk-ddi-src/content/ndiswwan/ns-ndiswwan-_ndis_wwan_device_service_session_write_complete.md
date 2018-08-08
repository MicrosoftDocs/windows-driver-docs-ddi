---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
title: "_NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE"
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure represents the status of a device service session write operation.
old-location: netvista\ndis_wwan_device_service_session_write_complete.htm
tech.root: netvista
ms.assetid: 16A48882-BEA6-4F95-8E9F-572BFD102031
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, netvista.ndis_wwan_device_service_session_write_complete"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
---

# _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure


## -description


The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure represents the status of a device service session write operation.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
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
NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the completion of the write operation.

