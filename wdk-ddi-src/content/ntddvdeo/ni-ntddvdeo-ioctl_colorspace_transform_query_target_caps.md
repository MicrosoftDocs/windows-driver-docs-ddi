---
UID: NI:ntddvdeo.IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS
title: IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS
author: windows-driver-content
description: A colorspace transform control IOCTL that must be handled by the monitor, OEM-panel, or port/miniport driver.
tech.root: display
ms.assetid: 7e6fa172-48c2-436a-a990-08089568ce76
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: ioctl
f1_keywords:
 - "ntddvdeo/IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS"
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
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddvdeo.h
api_name: 
 - IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# IOCTL_COLORSPACE_TRANSFORM_QUERY_TARGET_CAPS IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

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
For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
