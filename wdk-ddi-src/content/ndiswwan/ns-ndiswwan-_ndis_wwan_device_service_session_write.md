---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
title: "_NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE" (ndiswwan.h)
description: The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents device service session data to be sent from the host to the MB device.
old-location: netvista\ndis_wwan_device_service_session_write.htm
tech.root: netvista
ms.assetid: BF4A7BF6-6C39-4F75-BF76-848FF9241E52
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, netvista.ndis_wwan_device_service_session_write"
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
-	NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
---

# _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure


## -description


The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents device service session data to be sent from the host to the MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
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
NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field WriteData

The data to be sent to the MB device.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh831877">WWAN_DEVICE_SERVICE_SESSION_WRITE</a>
 

 

