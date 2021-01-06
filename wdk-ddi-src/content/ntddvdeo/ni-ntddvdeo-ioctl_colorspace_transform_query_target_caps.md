---
UID: NI:ntddvdeo.IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS
title: IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS
description: A colorspace transform control IOCTL that must be handled by the monitor, OEM-panel, or port/miniport driver.
tech.root: display
ms.date: 04/04/2019
keywords: ["IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS IOCTL"]
req.header: ntddvdeo.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS
 - ntddvdeo/IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS
dev_langs:
 - c++
---

# IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

A colorspace transform control IOCTL that must be handled by the monitor, OEM-panel, or port/miniport driver.

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
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
