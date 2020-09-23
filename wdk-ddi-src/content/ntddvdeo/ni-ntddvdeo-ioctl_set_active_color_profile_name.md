---
UID: NI:ntddvdeo.IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME
title: IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME
description: A colorspace transform control IOCTL that must be handled by the monitor, OEM-panel, or port/miniport driver.
tech.root: display
ms.assetid: f39b1114-70dd-4975-ba6e-058456f7f64d
ms.date: 04/04/2019
keywords: ["IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME IOCTL"]
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
 - IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME
 - ntddvdeo/IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddvdeo.h
api_name:
 - IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME
dev_langs:
 - c++
---

# IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)


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
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also

