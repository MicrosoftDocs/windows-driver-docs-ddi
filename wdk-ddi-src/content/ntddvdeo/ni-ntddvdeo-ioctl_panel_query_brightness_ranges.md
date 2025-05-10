---
UID: NI:ntddvdeo.IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
title: IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES (ntddvdeo.h)
description: Queries the brightness ranges for a display panel.
ms.date: 05/09/2025
req.header: ntddvdeo.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
tech.root: display
f1_keywords:
 - IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
 - ntddvdeo/IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
---

# IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES IOCTL

## -description

IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES queries the brightness ranges for a display panel.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

Set to NULL.

### -input-buffer-length

Set to 0.

### -output-buffer

A pointer to a caller-allocated buffer that receives the output data. The output is a [**PANEL_QUERY_BRIGHTNESS_RANGES**](ns-ntddvdeo-_panel_query_brightness_ranges.md) structure in which the queried brightness levels or nit ranges are returned.

### -output-buffer-length

The size, in bytes, of the output buffer. This value must be set to the size of the **PANEL_QUERY_BRIGHTNESS_RANGES** structure expected to be returned in the output buffer.

### -in-out-buffer

n/a

### -inout-buffer-length

n/a

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful. Otherwise, it's set to the appropriate error condition as a NTSTATUS code.

## -see-also

[**PANEL_QUERY_BRIGHTNESS_RANGES**](ns-ntddvdeo-_panel_query_brightness_ranges.md)
