---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE_FAILURE_FLAGS
title: "_USBDEVICE_UPDATE_FAILURE_FLAGS"
description: The flags that are set by the client driver in the EVT_UCX_USBDEVICE_UPDATE callback function. Indicate errors, if any, that might have occurred while updating the device.
old-location: buses\_usbdevice_update_failure_flags.htm
tech.root: usbref
ms.assetid: D01F8C2D-4E17-4FB7-A3C6-4B7EEDF07E0D
ms.date: 05/07/2018
ms.keywords: P_USBDEVICE_UPDATE_FAILURE_FLAGS, P_USBDEVICE_UPDATE_FAILURE_FLAGS structure pointer [Buses], USBDEVICE_UPDATE_FAILURE_FLAGS, USBDEVICE_UPDATE_FAILURE_FLAGS structure [Buses], _USBDEVICE_UPDATE_FAILURE_FLAGS, buses._usbdevice_update_failure_flags, ucxusbdevice/P_USBDEVICE_UPDATE_FAILURE_FLAGS, ucxusbdevice/_USBDEVICE_UPDATE_FAILURE_FLAGS
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
-	USBDEVICE_UPDATE_FAILURE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_UPDATE_FAILURE_FLAGS
---

# _USBDEVICE_UPDATE_FAILURE_FLAGS structure


## -description


The flags that are set by the client driver in the  <a href="https://msdn.microsoft.com/library/windows/hardware/mt187846">EVT_UCX_USBDEVICE_UPDATE</a> callback function. Indicate errors, if any, that might have occurred while updating the device.


## -struct-fields




### -field MaxExitLatencyTooLarge

The maximum exit latency is larger than expected.


### -field Reserved

Do not use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188080">USBDEVICE_UPDATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188081">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188083">USBDEVICE_UPDATE_FLAGS</a>
 

 

