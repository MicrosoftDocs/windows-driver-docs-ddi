---
UID: NF:ndis.NdisFDevicePnPEventNotify
title: NdisFDevicePnPEventNotify function
author: windows-driver-content
description: A filter driver can call the NdisFDevicePnPEventNotify function to forward a device Plug and Play (PnP) or Power Management event to underlying drivers.
old-location: netvista\ndisfdevicepnpeventnotify.htm
old-project: netvista
ms.assetid: ae5dd48b-7777-4232-89ad-ac4464e03e57
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFDevicePnPEventNotify, NdisFDevicePnPEventNotify function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_56e249ae-0200-4c98-b20c-03cc8d3fdd7d.xml, ndis/NdisFDevicePnPEventNotify, netvista.ndisfdevicepnpeventnotify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFDevicePnPEventNotify
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFDevicePnPEventNotify function


## -description


A filter driver can call the 
  <b>NdisFDevicePnPEventNotify</b> function to forward a device Plug and Play (PnP) or Power Management event
  to underlying drivers.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -param NetDevicePnPEvent [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568730">NET_DEVICE_PNP_EVENT</a> structure that
     describes a device Plug and Play event.


## -returns



None




## -remarks



NDIS calls a filter driver's 
    <a href="https://msdn.microsoft.com/dea4ab30-ba1d-4c9c-9f00-e48cc3cc0b46">
    FilterDevicePnPEventNotify</a> function to notify the filter driver of device PnP and Power Management
    events that affect an underlying device object.

Filter drivers can forward these notifications to underlying drivers. To forward a request, call the 
    <b>NdisFDevicePnPEventNotify</b> function before returning from the 
    <i>FilterDevicePnPEventNotify</i> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/dea4ab30-ba1d-4c9c-9f00-e48cc3cc0b46">FilterDevicePnPEventNotify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568730">NET_DEVICE_PNP_EVENT</a>
 

 

