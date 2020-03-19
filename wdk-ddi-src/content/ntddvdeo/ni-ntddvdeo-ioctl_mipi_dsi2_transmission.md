---
UID: NI:ntddvdeo.IOCTL_MIPI_DSI2_TRANSMISSION
title: IOCTL_MIPI_DSI2_TRANSMISSION
author: windows-driver-content
description: Mipi (mobile industry processor interface) DCS IOCLTs must be handled by the monitor, oem-panel, or port/miniport driver.
tech.root: display
ms.assetid: 7292a449-2c3c-4409-a031-ffe6316767f6
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["IOCTL_MIPI_DSI2_TRANSMISSION IOCTL"]
f1_keywords:
 - "ntddvdeo/IOCTL_MIPI_DSI2_TRANSMISSION"
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
 - IOCTL_MIPI_DSI2_TRANSMISSION
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# IOCTL_MIPI_DSI2_TRANSMISSION IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

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
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
