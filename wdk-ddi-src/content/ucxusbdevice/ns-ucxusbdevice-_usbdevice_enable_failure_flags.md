---
UID: NS:ucxusbdevice._USBDEVICE_ENABLE_FAILURE_FLAGS
title: "_USBDEVICE_ENABLE_FAILURE_FLAGS"
author: windows-driver-content
description: The flags that are set by the client driver in the EVT_UCX_USBDEVICE_ENABLE callback function. Indicate errors, if any, that might have occurred while enabling the device.
old-location: buses\_usbdevice_enable_failure_flags.htm
old-project: usbref
ms.assetid: B239E637-2920-48A5-9F45-D3089140C8A2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: P_USBDEVICE_ENABLE_FAILURE_FLAGS, P_USBDEVICE_ENABLE_FAILURE_FLAGS structure pointer [Buses], USBDEVICE_ENABLE_FAILURE_FLAGS, USBDEVICE_ENABLE_FAILURE_FLAGS structure [Buses], _USBDEVICE_ENABLE_FAILURE_FLAGS, buses._usbdevice_enable_failure_flags, ucxusbdevice/P_USBDEVICE_ENABLE_FAILURE_FLAGS, ucxusbdevice/_USBDEVICE_ENABLE_FAILURE_FLAGS
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
-	USBDEVICE_ENABLE_FAILURE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_ENABLE_FAILURE_FLAGS
req.product: Windows 10 or later.
---

# _USBDEVICE_ENABLE_FAILURE_FLAGS structure


## -description


The flags that are set by the client driver in the  <a href="https://msdn.microsoft.com/library/windows/hardware/mt187841">EVT_UCX_USBDEVICE_ENABLE</a> callback function. Indicate errors, if any, that might have occurred while enabling the device.


## -struct-fields




### -field InsufficientHardwareResourcesForDefaultEndpoint

Insufficient  hardware resources for  transfers to the default endpoint. 


### -field InsufficientHardwareResourcesForDevice

Insufficient hardware resources to enable transfers.


### -field Reserved

Do not use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187841">EVT_UCX_USBDEVICE_ENABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188072">USBDEVICE_ENABLE</a>
 

 

