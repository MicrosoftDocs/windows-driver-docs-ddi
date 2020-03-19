---
UID: NS:ndiswwan._NDIS_WWAN_SUPPORTED_DEVICE_SERVICES
title: _NDIS_WWAN_SUPPORTED_DEVICE_SERVICES (ndiswwan.h)
description: The NDIS_WWAN_SUPPORTED_DEVICE_SERVICES structure describes a list of supported device services.
old-location: netvista\ndis_wwan_supported_device_services.htm
tech.root: netvista
ms.assetid: C94C4426-A487-422D-B84E-B29C2AD7BF0C
ms.date: 05/02/2018
keywords: ["_NDIS_WWAN_SUPPORTED_DEVICE_SERVICES structure"]
ms.keywords: "*PNDIS_WWAN_SUPPORTED_DEVICE_SERVICES, NDIS_WWAN_SUPPORTED_DEVICE_SERVICES, NDIS_WWAN_SUPPORTED_DEVICE_SERVICES structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SUPPORTED_DEVICE_SERVICES, PNDIS_WWAN_SUPPORTED_DEVICE_SERVICES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SUPPORTED_DEVICE_SERVICES, ndiswwan/NDIS_WWAN_SUPPORTED_DEVICE_SERVICES, ndiswwan/PNDIS_WWAN_SUPPORTED_DEVICE_SERVICES, netvista.ndis_wwan_supported_device_services"
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SUPPORTED_DEVICE_SERVICES"
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
- NDIS_WWAN_SUPPORTED_DEVICE_SERVICES
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SUPPORTED_DEVICE_SERVICES, *PNDIS_WWAN_SUPPORTED_DEVICE_SERVICES
---

# _NDIS_WWAN_SUPPORTED_DEVICE_SERVICES structure


## -description


The NDIS_WWAN_SUPPORTED_DEVICE_SERVICES structure describes a list of supported device services.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SUPPORTED_DEVICE_SERVICES
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
NDIS_WWAN_SUPPORTED_DEVICE_SERVICES_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SUPPORTED_DEVICE_SERVICES)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the device services query operation.


### -field DeviceServices

This member points to the list of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure that represents the list of supported device services and information about themby using the WWAN_LIST_HEADER structure


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a>
 

 

