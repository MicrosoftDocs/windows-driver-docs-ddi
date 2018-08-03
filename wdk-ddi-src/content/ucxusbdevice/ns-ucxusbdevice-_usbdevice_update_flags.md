---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE_FLAGS
title: "_USBDEVICE_UPDATE_FLAGS"
author: windows-driver-content
description: Contains request flags set by UCX that is passed in the USBDEVICE_UPDATE structure when UCX invokes the client driver's EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update_flags.htm
tech.root: usbref
ms.assetid: 36F009C8-046B-437A-83D6-AE8D5BF51AF3
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: P_USBDEVICE_UPDATE_FLAGS, P_USBDEVICE_UPDATE_FLAGS structure pointer [Buses], USBDEVICE_UPDATE_FLAGS, USBDEVICE_UPDATE_FLAGS structure [Buses], _USBDEVICE_UPDATE_FLAGS, buses._usbdevice_update_flags, ucxusbdevice/P_USBDEVICE_UPDATE_FLAGS, ucxusbdevice/_USBDEVICE_UPDATE_FLAGS
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
-	USBDEVICE_UPDATE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_UPDATE_FLAGS
---

# _USBDEVICE_UPDATE_FLAGS structure


## -description


Contains request flags set by UCX that is  passed in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188080">USBDEVICE_UPDATE</a> structure when UCX invokes the client driver's <a href="https://msdn.microsoft.com/library/windows/hardware/mt187846">EVT_UCX_USBDEVICE_UPDATE</a> callback function.


## -struct-fields




### -field UpdateDeviceDescriptor

If set, indicates a request to update the USB device descriptor.


### -field UpdateBosDescriptor

If set, indicates a request to update the USB BOS descriptor.


### -field UpdateMaxExitLatency

If set, indicates a request to update the maximum exit latency.


### -field UpdateIsHub

If set, indicates a request to determine of the device is a hub.


### -field UpdateAllowIoOnInvalidPipeHandles

If set, indicates the USB device or hub has been updated to allow I/O with invalid pipe handles.


### -field Update20HardwareLpmParameters

If set, indicates a request to update the 2.0 LPM state.


### -field UpdateRootPortResumeTime

If set, indicates a request to  update the root port resume time.


### -field Reserved

Do not use. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188080">USBDEVICE_UPDATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188081">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188082">USBDEVICE_UPDATE_FAILURE_FLAGS</a>
 

 

