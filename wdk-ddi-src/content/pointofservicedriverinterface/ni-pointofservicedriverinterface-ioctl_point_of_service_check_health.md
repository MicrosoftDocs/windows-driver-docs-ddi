---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
title: IOCTL_POINT_OF_SERVICE_CHECK_HEALTH (pointofservicedriverinterface.h)
description: This I/O control function checks the device health.
old-location: pos\ioctl_point_of_service_check_health.htm
tech.root: pos
ms.assetid: b11be48b-e791-4599-80da-2446791f3816
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_CHECK_HEALTH IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_CHECK_HEALTH, IOCTL_POINT_OF_SERVICE_CHECK_HEALTH control, IOCTL_POINT_OF_SERVICE_CHECK_HEALTH control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_CHECK_HEALTH, pos.ioctl_point_of_service_check_health
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
 - pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
---

# IOCTL_POINT_OF_SERVICE_CHECK_HEALTH IOCTL


## -description

This I/O control function checks the device health.

## -ioctlparameters

### -input-buffer

Pointer to the input buffer, a [UnifiedPosHealthCheckLevel](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedposhealthchecklevel) variable.

### -input-buffer-length

Size of the input buffer, in bytes. Set to sizeof(*UnifiedPosHealthCheckLevel*).

### -output-buffer

Pointer to a buffer that receives a [PosStringType](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posstringtype) followed by the contents of the health string.

### -output-buffer-length

Size of the output buffer, in bytes. Set to sizeof(*PosStringType*) + enough room to hold the health string.

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

## -remarks

To get extended error information, call [GetLastError](https://docs.microsoft.com/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). The following is a common error value:

- STATUS_NOT_SUPPORTED: The driver does not provide health strings.

