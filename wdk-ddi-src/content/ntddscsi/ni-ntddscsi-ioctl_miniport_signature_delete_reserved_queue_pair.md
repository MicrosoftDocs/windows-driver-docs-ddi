---
UID: NI:ntddscsi.IOCTL_MINIPORT_SIGNATURE_DELETE_RESERVED_QUEUE_PAIR
title: IOCTL_MINIPORT_SIGNATURE_DELETE_RESERVED_QUEUE_PAIR
author: windows-driver-content
description: 
ms.assetid: 50e2ad9f-3bb1-49e8-a694-6e0b28201aec
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
-	IOCTL_MINIPORT_SIGNATURE_DELETE_RESERVED_QUEUE_PAIR
product:
-	Windows
targetos: Windows
---

# IOCTL_MINIPORT_SIGNATURE_DELETE_RESERVED_QUEUE_PAIR IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

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
For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also