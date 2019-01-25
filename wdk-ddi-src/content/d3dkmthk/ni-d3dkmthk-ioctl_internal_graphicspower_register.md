---
UID: NI:d3dkmthk.IOCTL_INTERNAL_GRAPHICSPOWER_REGISTER
title: IOCTL_INTERNAL_GRAPHICSPOWER_REGISTER (d3dkmthk.h)
description: For internal use only. Do not use.
ms.assetid: 4f49199d-f3ba-455e-bda4-17d816e929ff
ms.date: 10/19/2018
ms.topic: ioctl
req.header: d3dkmthk.h
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
-	d3dkmthk.h
api_name: 
-	IOCTL_INTERNAL_GRAPHICSPOWER_REGISTER
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# IOCTL_INTERNAL_GRAPHICSPOWER_REGISTER IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

> [!IMPORTANT]
> For internal use only. Do not use.

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
