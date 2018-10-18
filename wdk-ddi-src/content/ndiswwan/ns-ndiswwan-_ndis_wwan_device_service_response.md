---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_RESPONSE
title: "_NDIS_WWAN_DEVICE_SERVICE_RESPONSE"
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure represents device service data from the transaction completion of a device service command.
old-location: netvista\ndis_wwan_device_service_response.htm
tech.root: netvista
ms.assetid: 65999499-C14C-45CC-B7A5-021750B1A728
ms.date: 5/2/2018
ms.keywords: "*PNDIS_WWAN_DEVICE_SERVICE_RESPONSE, NDIS_WWAN_DEVICE_SERVICE_RESPONSE, NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_SERVICE_RESPONSE, PNDIS_WWAN_DEVICE_SERVICE_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_RESPONSE, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_RESPONSE, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_RESPONSE, netvista.ndis_wwan_device_service_response"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_DEVICE_SERVICE_RESPONSE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_SERVICE_RESPONSE, *PNDIS_WWAN_DEVICE_SERVICE_RESPONSE
---

# _NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure


## -description


The NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure represents device service data from the transaction completion of a device service command.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_RESPONSE structure. The MB
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
NDIS_WWAN_DEVICE_SERVICE_RESPONSE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_RESPONSE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the completion of the command.


### -field Response

 




#### - ResponseData

The response from the completion of the device service command.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh831872">WWAN_DEVICE_SERVICE_RESPONSE</a>
 

 

