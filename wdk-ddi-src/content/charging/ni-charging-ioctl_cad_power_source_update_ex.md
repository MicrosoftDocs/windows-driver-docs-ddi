---
UID: NI:charging.IOCTL_CAD_POWER_SOURCE_UPDATE_EX
title: IOCTL_CAD_POWER_SOURCE_UPDATE_EX (charging.h)
description: The IOCTL_CAD_POWER_SOURCE_UPDATE_EX system call is for internal use only and should not be called from your code.
old-location: battery\ioctl_cad_power_source_update_ex.htm
tech.root: battery
ms.date: 02/15/2018
keywords: ["IOCTL_CAD_POWER_SOURCE_UPDATE_EX IOCTL"]
ms.keywords: IOCTL_CAD_POWER_SOURCE_UPDATE_EX, IOCTL_CAD_POWER_SOURCE_UPDATE_EX control, IOCTL_CAD_POWER_SOURCE_UPDATE_EX control code [Battery Devices], battery.ioctl_cad_power_source_update_ex, charging/IOCTL_CAD_POWER_SOURCE_UPDATE_EX
req.header: charging.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_CAD_POWER_SOURCE_UPDATE_EX
 - charging/IOCTL_CAD_POWER_SOURCE_UPDATE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - charging.h
api_name:
 - IOCTL_CAD_POWER_SOURCE_UPDATE_EX
---

# IOCTL_CAD_POWER_SOURCE_UPDATE_EX IOCTL


## -description

This IOCTL is for internal use only.

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
