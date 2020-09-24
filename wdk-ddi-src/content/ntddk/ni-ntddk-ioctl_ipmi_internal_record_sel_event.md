---
UID: NI:ntddk.IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT
title: IOCTL_IPMI_INTERNAL_RECORD_SEL_EVENT
description: 
tech.root: 
ms.assetid: 44246bf3-ec90-48b5-b444-7398b483b192
ms.date: 08/19/2019
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
ms.custom: 19H1
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

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

Reserved for system use.

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
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also