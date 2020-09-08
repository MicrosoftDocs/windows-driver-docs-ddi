---
UID: NI:ntddvdeo.IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS
title: IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS (ntddvdeo.h)
description: Queries the brightness capabilities for a display panel.
ms.assetid: e36d2980-28db-4770-acbb-db79c60049e6
ms.date: 10/19/2018
keywords: ["IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS IOCTL"]
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
 - IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS
 - ntddvdeo/IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS
product:
 - Windows
---

# IOCTL_PANEL_QUERY_BRIGHTNESS_CAPS IOCTL

## Major Code:  [[XREF-LINK:IRP_MJ_DEVICE_CONTROL]


## -description

Queries the brightness capabilities for a display panel.

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

