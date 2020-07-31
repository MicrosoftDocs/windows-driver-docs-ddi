---
UID: NI:ntddvdeo.IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION
title: IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION (ntddvdeo.h)
description: Sets the backlight optimization for the display panel.
ms.assetid: 706088f5-0157-4dbd-a475-dafe9811b5b1
ms.date: 10/19/2018
keywords: ["IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION IOCTL"]
f1_keywords:
 - "ntddvdeo/IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION"
 - "IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION"
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
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- ntddvdeo.h
api_name:
- IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION
product: 
- Windows
targetos: Windows
tech.root: display
---

# IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description

Sets the backlight optimization for the display panel.

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

