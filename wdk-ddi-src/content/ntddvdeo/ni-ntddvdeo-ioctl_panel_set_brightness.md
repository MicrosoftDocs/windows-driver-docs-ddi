---
UID: NI:ntddvdeo.IOCTL_PANEL_SET_BRIGHTNESS
title: IOCTL_PANEL_SET_BRIGHTNESS
author: windows-driver-content
description: Sets the brightness for the display panel.
ms.assetid: 7fa5e82d-90fa-4e99-a33d-c2519ff619aa
ms.date: 10/19/2018
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
-	IOCTL_PANEL_SET_BRIGHTNESS
product: 
- Windows
targetos: Windows
tech.root: display
---

# IOCTL_PANEL_SET_BRIGHTNESS IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description

Sets the brightness for the display panel.

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

