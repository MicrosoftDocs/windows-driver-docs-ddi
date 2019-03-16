---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION
title: _NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION (ndiswwan.h)
description: The NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structures encapsulates the data for NDIS_STATUS_WWAN_ DEVICE_SERVICE_SUBSCRIPTION.
old-location: netvista\ndis_wwan_device_service_subscription.htm
tech.root: netvista
ms.assetid: 65B9739B-98C6-441E-B15A-67C32A5FB232
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, PNDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, netvista.ndis_wwan_device_service_subscription"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndiswwan.h
api_name:
- NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, *PNDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION
---

# _NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structure


## -description


The NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structures encapsulates the data for NDIS_STATUS_WWAN_ DEVICE_SERVICE_SUBSCRIPTION.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structure. The MB
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
NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the device service subscription operation.

This can be any WWAN_STATUS code.


### -field DeviceServiceListHeader

A formatted WWAN_LIST_HEADER object that represents a list of device services and the number of services  in the list.  This is the list of device services for which the device would indicate NDIS_STATUS_WWAN_DEVICE_SERVICE_EVENT notifications.

This member points to the list of the GUIDs by using the WWAN_LIST_HEADER structure, and should contain 0 elements when indicated to mark completion of a set <a href="https://msdn.microsoft.com/library/windows/hardware/hh440096">OID_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS</a> request.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh440096">OID_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a>
 

 

