---
UID: NS:ndiswwan._NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS
title: "_NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS"
author: windows-driver-content
description: The NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure encapsulates data for OID_WWAN_SUBSCRIBE_DEVICE_SERVICES_EVENTS.
old-location: netvista\ndis_wwan_subscribe_device_service_events.htm
old-project: netvista
ms.assetid: 99A772EF-C67C-48B0-A3F9-0B32A14247D6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS, NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS, NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS, PNDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS, ndiswwan/NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS, ndiswwan/PNDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS, netvista.ndis_wwan_subscribe_device_service_events"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndiswwan.h
api_name:
-	NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS, *PNDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS
---

# _NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure


## -description


The NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure encapsulates data for OID_WWAN_SUBSCRIBE_DEVICE_SERVICES_EVENTS.


## -syntax


````
typedef struct _NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS {
  NDIS_OBJECT_HEADER Header;
  WWAN_LIST_HEADER   DeviceServiceListHeader;
} NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS, *PNDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS;
````


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure. The MB
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
NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field DeviceServiceListHeader

A formatted WWAN_LIST_HEADER object that represents a list of device services and the number of services  in the list.

This is the list of device service that the MB service has subscribed for NDIS_STATUS_WWAN_DEVICE_SERVICE_EVENT notifications.

This member points to the list of the GUIDs (WwanStructDeviceServiceGuid) by using the WWAN_LIST_HEADER structure.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_SUBSCRIBE_DEVICE_SERVICE_EVENTS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

