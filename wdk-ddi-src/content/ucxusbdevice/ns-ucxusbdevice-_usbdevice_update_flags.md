---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE_FLAGS
title: _USBDEVICE_UPDATE_FLAGS (ucxusbdevice.h)
description: Contains request flags set by UCX that is passed in the USBDEVICE_UPDATE structure when UCX invokes the client driver's EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update_flags.htm
tech.root: usbref
ms.date: 06/07/2022
keywords: ["USBDEVICE_UPDATE_FLAGS structure"]
ms.keywords: P_USBDEVICE_UPDATE_FLAGS, P_USBDEVICE_UPDATE_FLAGS structure pointer [Buses], USBDEVICE_UPDATE_FLAGS, USBDEVICE_UPDATE_FLAGS structure [Buses], _USBDEVICE_UPDATE_FLAGS, buses._usbdevice_update_flags, ucxusbdevice/P_USBDEVICE_UPDATE_FLAGS, ucxusbdevice/_USBDEVICE_UPDATE_FLAGS
req.header: ucxusbdevice.h
req.construct-type: structure
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
targetos: Windows
req.typenames: USBDEVICE_UPDATE_FLAGS
f1_keywords:
 - _USBDEVICE_UPDATE_FLAGS
 - ucxusbdevice/_USBDEVICE_UPDATE_FLAGS
 - USBDEVICE_UPDATE_FLAGS
 - ucxusbdevice/USBDEVICE_UPDATE_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxusbdevice.h
api_name:
 - _USBDEVICE_UPDATE_FLAGS
 - USBDEVICE_UPDATE_FLAGS
---

# USBDEVICE_UPDATE_FLAGS structure (ucxusbdevice.h)



## -description

Contains request flags set by UCX that is passed in the [USBDEVICE_UPDATE](ns-ucxusbdevice-_usbdevice_update.md) structure when UCX invokes the client driver's [EVT_UCX_USBDEVICE_UPDATE](nc-ucxusbdevice-evt_ucx_usbdevice_update.md) callback function.

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

### -field UpdateTunnelState

If set, indicates a request to update the USB tunnel state.

### -field Reserved

Do not use.

## -see-also

- [USBDEVICE_UPDATE](ns-ucxusbdevice-_usbdevice_update.md)
- [USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS](ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md)
- [USBDEVICE_UPDATE_FAILURE_FLAGS](ns-ucxusbdevice-_usbdevice_update_failure_flags.md)
