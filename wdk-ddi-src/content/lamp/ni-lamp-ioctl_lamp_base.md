---
UID: NI:lamp.IOCTL_LAMP_BASE
title: IOCTL_LAMP_BASE (lamp.h)
description: 
ms.assetid: 91ad561c-3f84-4395-8612-bd7a836b6e24
ms.date: 10/19/2018
keywords: ["IOCTL_LAMP_BASE IOCTL"]
f1_keywords:
 - "lamp/IOCTL_LAMP_BASE"
 - "IOCTL_LAMP_BASE"
req.header: lamp.h
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
- lamp.h
api_name: 
- IOCTL_LAMP_BASE
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# IOCTL_LAMP_BASE IOCTL

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
