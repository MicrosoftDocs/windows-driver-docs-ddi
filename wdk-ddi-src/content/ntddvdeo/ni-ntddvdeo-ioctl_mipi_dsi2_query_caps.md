---
UID: NI:ntddvdeo.IOCTL_MIPI_DSI2_QUERY_CAPS
title: IOCTL_MIPI_DSI2_QUERY_CAPS
author: windows-driver-content
description: Mipi (mobile industry processor interface) DCS IOCLTs must be handled by the monitor, oem-panel, or port/miniport driver.
tech.root: display
ms.assetid: 8472c449-74ee-4590-a94b-7d726e1707db
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: ioctl
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
 - IOCTL_MIPI_DSI2_QUERY_CAPS
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# IOCTL_MIPI_DSI2_QUERY_CAPS IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

Mipi (mobile industry processor interface) DCS IOCLTs must be handled by the monitor, oem-panel, or port/miniport driver.

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
