---
UID: NI:ntddscsi.IOCTL_MINIPORT_SIGNATURE_QUERY_QUEUE_INFO
title: IOCTL_MINIPORT_SIGNATURE_QUERY_QUEUE_INFO (ntddscsi.h)
author: mimisasouvanh
ms.author: misaso
description: 
ms.assetid: 04498f2d-a468-4b94-a762-5234e0d220a5
ms.date: 10/19/2018
f1_keywords:
 - "ntddscsi/IOCTL_MINIPORT_SIGNATURE_QUERY_QUEUE_INFO"
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
- apiref
api_type: 
- HeaderDef
api_location: 
- ntddscsi.h
api_name: 
- IOCTL_MINIPORT_SIGNATURE_QUERY_QUEUE_INFO
product:
- Windows
targetos: Windows
---

# IOCTL_MINIPORT_SIGNATURE_QUERY_QUEUE_INFO IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

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
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
