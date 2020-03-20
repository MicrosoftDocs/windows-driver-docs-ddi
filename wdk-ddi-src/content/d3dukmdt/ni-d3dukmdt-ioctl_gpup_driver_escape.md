---
UID: NI:d3dukmdt.IOCTL_GPUP_DRIVER_ESCAPE
title: IOCTL_GPUP_DRIVER_ESCAPE (d3dukmdt.h)
description: The user mode emulation DLL calls this IOCTL to exchange information with the kernel mode driver.
ms.assetid: 02ba7385-fda9-45a9-820d-311fc35258dc
ms.date: 10/19/2018
keywords: ["IOCTL_GPUP_DRIVER_ESCAPE IOCTL"]
f1_keywords:
 - "d3dukmdt/IOCTL_GPUP_DRIVER_ESCAPE"
req.header: d3dukmdt.h
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
- d3dukmdt.h
api_name: 
- IOCTL_GPUP_DRIVER_ESCAPE
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# IOCTL_GPUP_DRIVER_ESCAPE IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description

The user mode emulation DLL calls this IOCTL to exchange information with the kernel mode driver.


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
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
