---
UID: NI:ntddvdeo.IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
title: IOCTL_PANEL_GET_BACKLIGHT_REDUCTION (ntddvdeo.h)
description: Panel control IOCTLs must/can be handled by the monitor, OEM panel, or port/miniport driver.
ms.date: 10/19/2018
keywords: ["IOCTL_PANEL_GET_BACKLIGHT_REDUCTION IOCTL"]
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
 - IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
 - ntddvdeo/IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
product:
 - Windows
---

# IOCTL_PANEL_GET_BACKLIGHT_REDUCTION IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]


## -description

Panel control IOCTLs must/can be handled by the monitor, OEM panel, or port/miniport driver.

## -ioctlparameters

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.

