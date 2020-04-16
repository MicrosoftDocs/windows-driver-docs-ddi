---
UID: NI:trustedrt.IOCTL_TR_ENUMERATE_SERVICES
title: IOCTL_TR_ENUMERATE_SERVICES (trustedrt.h)
description: 
ms.assetid: de6f27ed-7fb3-4cf1-953c-e683ffdbf475
ms.date: 10/19/2018
keywords: ["IOCTL_TR_ENUMERATE_SERVICES IOCTL"]
f1_keywords:
 - "trustedrt/IOCTL_TR_ENUMERATE_SERVICES"
req.header: trustedrt.h
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
- trustedrt.h
api_name: 
- IOCTL_TR_ENUMERATE_SERVICES
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# IOCTL_TR_ENUMERATE_SERVICES IOCTL

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
