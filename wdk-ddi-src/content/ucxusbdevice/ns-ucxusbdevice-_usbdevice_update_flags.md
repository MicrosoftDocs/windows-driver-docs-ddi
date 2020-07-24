---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE_FLAGS
title: _USBDEVICE_UPDATE_FLAGS (ucxusbdevice.h)
description: Contains request flags set by UCX that is passed in the USBDEVICE_UPDATE structure when UCX invokes the client driver's EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update_flags.htm
tech.root: usbref
ms.assetid: 36F009C8-046B-437A-83D6-AE8D5BF51AF3
ms.date: 05/07/2018
keywords: ["_USBDEVICE_UPDATE_FLAGS structure"]
ms.keywords: P_USBDEVICE_UPDATE_FLAGS, P_USBDEVICE_UPDATE_FLAGS structure pointer [Buses], USBDEVICE_UPDATE_FLAGS, USBDEVICE_UPDATE_FLAGS structure [Buses], _USBDEVICE_UPDATE_FLAGS, buses._usbdevice_update_flags, ucxusbdevice/P_USBDEVICE_UPDATE_FLAGS, ucxusbdevice/_USBDEVICE_UPDATE_FLAGS
f1_keywords:
 - "ucxusbdevice/USBDEVICE_UPDATE_FLAGS"
 - "USBDEVICE_UPDATE_FLAGS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucxusbdevice.h
api_name:
- USBDEVICE_UPDATE_FLAGS
targetos: Windows
req.typenames: USBDEVICE_UPDATE_FLAGS
---

# _USBDEVICE_UPDATE_FLAGS structure


## -description


Contains request flags set by UCX that is  passed in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update">USBDEVICE_UPDATE</a> structure when UCX invokes the client driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_update">EVT_UCX_USBDEVICE_UPDATE</a> callback function.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update">USBDEVICE_UPDATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_update_failure_flags">USBDEVICE_UPDATE_FAILURE_FLAGS</a>
 

 

