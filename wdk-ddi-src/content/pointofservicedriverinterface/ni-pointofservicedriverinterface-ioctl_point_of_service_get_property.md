---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_GET_PROPERTY
title: IOCTL_POINT_OF_SERVICE_GET_PROPERTY (pointofservicedriverinterface.h)
description: This I/O control function returns the value of the specified property from the device driver.
old-location: pos\ioctl_point_of_service_get_property.htm
tech.root: pos
ms.assetid: 7d0231b3-4db7-47b3-8208-70d2cd337005
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_GET_PROPERTY IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_GET_PROPERTY, IOCTL_POINT_OF_SERVICE_GET_PROPERTY control, IOCTL_POINT_OF_SERVICE_GET_PROPERTY control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_GET_PROPERTY, pos.ioctl_point_of_service_get_property
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_GET_PROPERTY"
 - "IOCTL_POINT_OF_SERVICE_GET_PROPERTY"
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
- IOCTL_POINT_OF_SERVICE_GET_PROPERTY
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_GET_PROPERTY IOCTL

## -description

This I/O control function returns the value of the specified property from the device driver.

## -ioctlparameters

### -input-buffer

Pointer to a buffer that contains the [PosPropertyId](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ne-pointofservicedriverinterface-_pospropertyid) for the property you want to get.

### -input-buffer-length

Size, in bytes, of the buffer pointed to by *lpInBuffer*. Set to sizeof(*PosPropertyId*).

### -output-buffer

Pointer to a buffer that receives the property value.

### -output-buffer-length

Size, in bytes, of the buffer pointed to by *lpOutBuffer*.

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

## -remarks

To get extended error information, call [GetLastError](https://docs.microsoft.com/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). The following list shows common error values (other status values may be returned as defined by your GET property callback implementation):

- STATUS_ACCESS_DENIED: The calling thread does not have a claim on the device.

- STATUS_BUFFER_OVERFLOW: The output buffer is not large enough to contain the output value. The driver will copy as much data into the output buffer as possible.
