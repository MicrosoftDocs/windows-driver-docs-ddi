---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_RESET_STATISTICS
title: IOCTL_POINT_OF_SERVICE_RESET_STATISTICS (pointofservicedriverinterface.h)
description: This I/O control function resets the specified statistic's value to zero.
old-location: pos\ioctl_point_of_service_reset_statistics.htm
tech.root: pos
ms.assetid: dfa6a460-ea80-4aa4-9948-2fd290f6616b
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_RESET_STATISTICS IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_RESET_STATISTICS, IOCTL_POINT_OF_SERVICE_RESET_STATISTICS control, IOCTL_POINT_OF_SERVICE_RESET_STATISTICS control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RESET_STATISTICS, pos.ioctl_point_of_service_reset_statistics
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RESET_STATISTICS"
 - "IOCTL_POINT_OF_SERVICE_RESET_STATISTICS"
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
- IOCTL_POINT_OF_SERVICE_RESET_STATISTICS
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_RESET_STATISTICS IOCTL

## -description

This I/O control function resets the specified statistic's value to zero.

## -ioctlparameters

### -input-buffer

[PosStringType](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posstringtype) that names the statistic to reset to zero.

### -input-buffer-length

Size of the string passed in *lpInBuffer*. Set to sizeof(*PosStringType*) + the size of the string in bytes.

### -output-buffer

Not used with this operation; set to **NULL**.

### -output-buffer-length

Not used with this operation; set to **0** (zero).

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

## -remarks

To get extended error information, call [GetLastError](https://docs.microsoft.com/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). The following is a common error value:

- STATUS_NOT_SUPPORTED: Statistic updating or reporting is not supported.
