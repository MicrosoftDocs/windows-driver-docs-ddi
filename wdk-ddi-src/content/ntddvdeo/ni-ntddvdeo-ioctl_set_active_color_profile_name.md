---
UID: NI:ntddvdeo.IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME
title: IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME
description: IOCTL_SET_ACTIVE_COLOR_PROFILE_NAME is a colorspace transform control IOCTL that must be handled by the monitor, OEM-panel, or port/miniport driver.
tech.root: display
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

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

A colorspace transform control IOCTL that must be handled by the monitor, OEM-panel, or port/miniport driver.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer


### -input-buffer-length 


### -output-buffer


### -output-buffer-length 


### -in-out-buffer


### -inout-buffer-length 


### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
