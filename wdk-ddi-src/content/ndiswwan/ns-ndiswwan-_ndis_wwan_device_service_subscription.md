---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION
title: _NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structures encapsulates the data for NDIS_STATUS_WWAN_ DEVICE_SERVICE_SUBSCRIPTION.
old-location: netvista\ndis_wwan_device_service_subscription.htm
old-project: netvista
ms.assetid: 65B9739B-98C6-441E-B15A-67C32A5FB232
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, *PNDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION
req.alt-loc: ndiswwan.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PNDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION
---

# _NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structure



## -description
The NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structures encapsulates the data for NDIS_STATUS_WWAN_ DEVICE_SERVICE_SUBSCRIPTION.



## -syntax

````
typedef struct _NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_LIST_HEADER   DeviceServiceListHeader;
} NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION, *PNDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION;
````


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
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the device service subscription operation.

This can be any WWAN_STATUS code.


### -field DeviceServiceListHeader

A formatted WWAN_LIST_HEADER object that represents a list of device services and the number of services  in the list.  This is the list of device services for which the device would indicate NDIS_STATUS_WWAN_DEVICE_SERVICE_EVENT notifications.

This member points to the list of the GUIDs by using the WWAN_LIST_HEADER structure, and should contain 0 elements when indicated to mark completion of a set <a href="https://msdn.microsoft.com/library/windows/hardware/hh440096">OID_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS</a> request.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh440096">OID_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_DEVICE_SERVICE_SUBSCRIPTION structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

