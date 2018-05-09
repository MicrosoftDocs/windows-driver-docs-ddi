---
UID: NI:ntddvdeo.IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS
title: IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS
author: windows-driver-content
description:
ms.assetid: e36d2980-28db-4770-acbb-db79c60049e6
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
-	IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS
product: Windows
targetos: Windows
---

# IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description

Queries the brightness capabilities for a display panel.

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


