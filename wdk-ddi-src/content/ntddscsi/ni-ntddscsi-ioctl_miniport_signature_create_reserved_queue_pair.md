---
UID: NI:ntddscsi.IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR
title: IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR (ntddscsi.h)
description: 
ms.assetid: 48859d1c-b9c2-4d44-944f-43b88d528964
ms.date: 10/19/2018
tech.root: storage
keywords: ["IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR IOCTL"]
f1_keywords:
 - "ntddscsi/IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR"
 - "IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR"
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
- IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR
targetos: Windows
---

# IOCTL_MINIPORT_SIGNATURE_CREATE_RESERVED_QUEUE_PAIR IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

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
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also