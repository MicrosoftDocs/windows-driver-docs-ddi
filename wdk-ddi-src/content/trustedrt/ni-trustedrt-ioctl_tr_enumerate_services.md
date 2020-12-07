---
UID: NI:trustedrt.IOCTL_TR_ENUMERATE_SERVICES
title: IOCTL_TR_ENUMERATE_SERVICES (trustedrt.h)
description: 
ms.date: 11/20/2020
keywords: ["IOCTL_TR_ENUMERATE_SERVICES IOCTL"]
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
targetos: Windows
ms.custom: RS5
tech.root: treedrv
f1_keywords:
 - IOCTL_TR_ENUMERATE_SERVICES
 - trustedrt/IOCTL_TR_ENUMERATE_SERVICES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - trustedrt.h
api_name:
 - IOCTL_TR_ENUMERATE_SERVICES
---

# IOCTL_TR_ENUMERATE_SERVICES IOCTL

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

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

## -see-also
