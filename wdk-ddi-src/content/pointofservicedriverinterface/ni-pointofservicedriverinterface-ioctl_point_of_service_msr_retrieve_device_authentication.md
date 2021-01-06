---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
title: IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION (pointofservicedriverinterface.h)
description: This I/O control function retrieves the device authentication type.
old-location: pos\ioctl_point_of_service_msr_retrieve_device_authentication.htm
tech.root: pos
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION, IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION control, IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION, pos.ioctl_point_of_service_msr_retrieve_device_authentication
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
 - IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
 - pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
---

# IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION IOCTL


## -description

This I/O control function retrieves the device authentication type.

## -ioctlparameters

### -input-buffer

Not used with this operation; set to **NULL**.

### -input-buffer-length

Not used with this operation; set to **0** (zero).

### -output-buffer

Pointer to a buffer that receives a [MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA](./ns-pointofservicedriverinterface-_msr_retrieve_device_authentication_data.md).

### -output-buffer-length

Size of the output buffer, in bytes. Set to sizeof(**MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA**).

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

To get extended error information, call [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

## -remarks
