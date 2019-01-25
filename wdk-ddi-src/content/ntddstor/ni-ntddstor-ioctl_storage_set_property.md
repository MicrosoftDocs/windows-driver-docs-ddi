---
UID: NI:ntddstor.IOCTL_STORAGE_SET_PROPERTY
title: IOCTL_STORAGE_SET_PROPERTY (ntddstor.h)
description: 
ms.assetid: 93fb0e92-a17b-4aa5-af19-05c510d66388
ms.date: 10/19/2018
ms.topic: ioctl
req.header: ntddstor.h
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
-	ntddstor.h
api_name: 
-	IOCTL_STORAGE_SET_PROPERTY
product:
-	Windows
targetos: Windows
---

# IOCTL_STORAGE_SET_PROPERTY IOCTL

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
