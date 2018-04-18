---
UID: NI:ntddscsi.IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR
title: IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR
author: windows-driver-content
description: 
ms.assetid: 48859d1c-b9c2-4d44-944f-43b88d528964
ms.author: windowsdriverdev
ms.date: 
ms.topic: ioctl
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ntddscsi.h
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
-	ntddscsi.h
api_name: 
-	IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR
product: Windows
targetos: Windows
---

# IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description




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