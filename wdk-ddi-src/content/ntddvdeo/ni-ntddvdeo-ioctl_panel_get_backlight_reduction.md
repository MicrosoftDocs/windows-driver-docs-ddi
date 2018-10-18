---
UID: NI:ntddvdeo.IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
title: IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
author: windows-driver-content
description: Panel control IOCTLs must/can be handled by the monitor, OEM panel, or port/miniport driver.
ms.assetid: 376241d5-082c-45b2-b7bf-b6fe5dd4eb39
ms.date:
ms.topic: ioctl
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
-	apiref
api_type:
-	HeaderDef
api_location:
-	ntddvdeo.h
api_name:
-	IOCTL_PANEL_GET_BACKLIGHT_REDUCTION
product: 
- Windows
targetos: Windows
tech.root: display
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

