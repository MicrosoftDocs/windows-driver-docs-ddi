---
UID: NI:trustedrt.IOCTL_TR_SERVICE_QUERY
title: IOCTL_TR_SERVICE_QUERY (trustedrt.h)
description: 
ms.assetid: f22825f0-a287-4343-a971-1e8765d0c199
ms.date: 10/19/2018
keywords: ["IOCTL_TR_SERVICE_QUERY IOCTL"]
f1_keywords:
 - "trustedrt/IOCTL_TR_SERVICE_QUERY"
 - "IOCTL_TR_SERVICE_QUERY"
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
- IOCTL_TR_SERVICE_QUERY
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# IOCTL_TR_SERVICE_QUERY IOCTL

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
