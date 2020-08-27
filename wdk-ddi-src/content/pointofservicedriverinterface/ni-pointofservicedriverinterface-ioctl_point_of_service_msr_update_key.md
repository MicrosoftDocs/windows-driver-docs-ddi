---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY
title: IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY (pointofservicedriverinterface.h)
description: This I/O control function sets a new encryption key.
old-location: pos\ioctl_point_of_service_msr_update_key.htm
tech.root: pos
ms.assetid: 7ac830d3-6a75-4d82-9123-cd7ad9c2cdea
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY, IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY control, IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY, pos.ioctl_point_of_service_msr_update_key
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY"
 - "IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY"
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pointofservicedriverinterface.h
api_name:
- IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY IOCTL

## -description

This I/O control function sets a new encryption key.

## -ioctlparameters

### -input-buffer

Pointer to the input buffer, a [MSR_UPDATE_KEY](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_msr_update_key) variable.

### -input-buffer-length

Size of the input buffer, in bytes. Set to **sizeof(MSR_UPDATE_KEY)**.

### -output-buffer

Not used with this operation; set to **NULL**.

### -output-buffer-length

Not used with this operation; set to **0** (zero).

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

To get extended error information, call [GetLastError](https://docs.microsoft.com/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)

## -remarks
