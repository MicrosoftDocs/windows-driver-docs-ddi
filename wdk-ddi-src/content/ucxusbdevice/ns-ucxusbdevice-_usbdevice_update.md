---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE
title: _USBDEVICE_UPDATE (ucxusbdevice.h)
description: Passed by UCX to update the specified device. This structure is in the request parameters (Parameters.Others.Arg1) of a framework request object passed in the EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update.htm
tech.root: usbref
ms.date: 01/14/2022
keywords: ["USBDEVICE_UPDATE structure"]
ms.keywords: "*PUSBDEVICE_UPDATE, P_USBDEVICE_UPDATE, P_USBDEVICE_UPDATE structure pointer [Buses], USBDEVICE_UPDATE, USBDEVICE_UPDATE structure [Buses], _USBDEVICE_UPDATE, buses._usbdevice_update, ucxusbdevice/P_USBDEVICE_UPDATE, ucxusbdevice/_USBDEVICE_UPDATE"
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
targetos: Windows
req.typenames: USBDEVICE_UPDATE, *PUSBDEVICE_UPDATE
f1_keywords:
 - _USBDEVICE_UPDATE
 - ucxusbdevice/_USBDEVICE_UPDATE
 - PUSBDEVICE_UPDATE
 - ucxusbdevice/PUSBDEVICE_UPDATE
 - USBDEVICE_UPDATE
 - ucxusbdevice/USBDEVICE_UPDATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxusbdevice.h
api_name:
 - _USBDEVICE_UPDATE
 - PUSBDEVICE_UPDATE
 - USBDEVICE_UPDATE
---

# _USBDEVICE_UPDATE structure

## -description

Passed by UCX to update the specified device. This structure is in the request parameters (**Parameters.Others.Arg1**) of a framework request object passed in the [EVT_UCX_USBDEVICE_UPDATE](nc-ucxusbdevice-evt_ucx_usbdevice_update.md) callback function.

## -struct-fields

### -field Header

A [USBDEVICE_MGMT_HEADER](ns-ucxusbdevice-_usbdevice_mgmt_header.md) structure that contains  the handle for the USB hub or device.

### -field Flags

A bitwise-OR of [USBDEVICE_UPDATE_FLAGS](ns-ucxusbdevice-_usbdevice_update_flags.md) values that indicates the attributes that must be updated by the client driver.

### -field DeviceDescriptor

A pointer a [USB_DEVICE_DESCRIPTOR](../usbspec/ns-usbspec-_usb_device_descriptor.md) structure that contains the device descriptor.

### -field BosDescriptor

A pointer a **USB_BOS_DESCRIPTOR** structure that contains the device descriptor. See Usbspec.h.

### -field MaxExitLatency

The maximum exit latency period.

### -field IsHub

Indicates if the USB device to update is a USB hub (TRUE) or not (FALSE).

### -field FailureFlags

A [USBDEVICE_UPDATE_FAILURE_FLAGS](ns-ucxusbdevice-_usbdevice_update_failure_flags.md) structure that indicates the errors, if any, that occurred during the update operation.

### -field Usb20HardwareLpmParameters

A [USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS](ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md) structure that describes the Link Power Management (LPM) features.

### -field RootPortResumeTime

The resume time for the root port.

## -see-also

- [USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS](ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md)
- [USBDEVICE_UPDATE_FAILURE_FLAGS](ns-ucxusbdevice-_usbdevice_update_failure_flags.md)
- [USBDEVICE_UPDATE_FLAGS](ns-ucxusbdevice-_usbdevice_update_flags.md)
- [WdfRequestGetParameters](../wdfrequest/nf-wdfrequest-wdfrequestgetparameters.md)
