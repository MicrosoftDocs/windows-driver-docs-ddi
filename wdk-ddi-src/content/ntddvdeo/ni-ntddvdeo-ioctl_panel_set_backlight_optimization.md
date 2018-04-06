---
UID: NI:ntddvdeo.IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION
title: IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION
author: windows-driver-content
description:
ms.assetid: 706088f5-0157-4dbd-a475-dafe9811b5b1
ms.author: windowsdriverdev
ms.date:
ms.topic: ioctl
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	ntddvdeo.h
apiname:
-	IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION
product: Windows
targetos: Windows
---

# IOCTL_PANEL_SET_BACKLIGHT_OPTIMIZATION IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description

Sets the backlight optimization for the display panel.

## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code.

