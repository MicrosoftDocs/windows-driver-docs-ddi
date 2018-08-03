---
UID: NI:ntddvdeo.IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
title: IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
author: windows-driver-content
description:
ms.assetid: 376241d5-082c-45b2-b7bf-b6fe5dd4eb39
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
-	IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
product: 
- Windows
targetos: Windows
---

# IOCTL_PANEL_GET_BACKLIGHT_REDUCTION IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description

Panel control IOCLTs must/can be handled by the monitor, OEM panel, or port/miniport driver.

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

