---
UID: NS:ucxusbdevice._USBDEVICE_HUB_INFO
title: "_USBDEVICE_HUB_INFO"
author: windows-driver-content
description: Contains parameters for a request to get information about the specified hub. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_HUB_INFO callback function.
old-location: buses\_usbdevice_hub_info.htm
old-project: usbref
ms.assetid: F403179A-B339-432D-AAF9-E7D9965F8B00
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBDEVICE_HUB_INFO, P_USBDEVICE_HUB_INFO, P_USBDEVICE_HUB_INFO structure pointer [Buses], USBDEVICE_HUB_INFO, USBDEVICE_HUB_INFO structure [Buses], _USBDEVICE_HUB_INFO, buses._usbdevice_hub_info, ucxusbdevice/P_USBDEVICE_HUB_INFO, ucxusbdevice/_USBDEVICE_HUB_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ucxusbdevice.h
api_name:
-	USBDEVICE_HUB_INFO
product: Windows
targetos: Windows
req.typenames: USBDEVICE_HUB_INFO, *PUSBDEVICE_HUB_INFO
req.product: Windows 10 or later.
---

# _USBDEVICE_HUB_INFO structure


## -description


Contains parameters for a request to get information about the specified hub. This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187844">EVT_UCX_USBDEVICE_HUB_INFO</a> callback function.


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field NumberOfPorts

The count of ports available for the USB hub, filled by the client driver.


### -field NumberOfTTs

The count of TT hubs, filled by the client driver.


### -field TTThinkTime

The ThinkTime property of the TT hub, filled by the client driver.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187844">EVT_UCX_USBDEVICE_HUB_INFO</a>
 

 

