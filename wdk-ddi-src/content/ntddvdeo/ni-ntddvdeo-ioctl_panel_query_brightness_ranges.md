---
UID: NI:ntddvdeo.IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
title: IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
author: windows-driver-content
description:
ms.assetid: 2fb0a064-2c67-46e0-baa9-d03394614d87
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
-	IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES
product: 
- Windows
targetos: Windows
---

# IOCTL_PANEL_QUERY_BRIGHTNESS_RANGES IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description

Queries the brightness ranges for a display panel.

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


