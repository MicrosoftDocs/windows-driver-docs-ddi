---
UID: NI:ntddk.IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT
title: IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT
description: "Learn more about: IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT IOCTL"
tech.root: whea
ms.date: 08/04/2021
keywords: ["IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT IOCTL"]
req.header: ntddk.h
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
f1_keywords:
 - IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT
 - ntddk/IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT
product:
 - Windows
---

# IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT IOCTL

## Major Code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

Reserved for system use.

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
