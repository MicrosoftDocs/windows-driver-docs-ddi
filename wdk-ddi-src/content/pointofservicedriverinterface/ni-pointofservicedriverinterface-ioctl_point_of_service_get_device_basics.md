---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS
title: IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS (pointofservicedriverinterface.h)
description: This I/O control function gets the type of device, version, and recommended buffer size as specified by the driver.
old-location: pos\ioctl_point_of_service_get_device_basics.htm
tech.root: pos
ms.assetid: dca09bfc-97cc-43b8-bf57-3d7c2b0321a9
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS, IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS control, IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS, pos.ioctl_point_of_service_get_device_basics
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
 - IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS
 - pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS
---

# IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS IOCTL


## -description

This I/O control function gets the type of device, version, and recommended buffer size as specified by the driver.

## -ioctlparameters

### -input-buffer

32-bit encoded POS Windows Runtime (WinRT) API version. The top sixteen bits must contain the major version, and the lower sixteen bits must contain the minor version.

### -input-buffer-length

Size of the input buffer, in bytes. Set to sizeof(UINT32).

### -output-buffer

Pointer to a buffer that receives a [PosDeviceBasicsType](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posdevicebasicstype).

### -output-buffer-length

Size of the output buffer, in bytes. Set to sizeof(*PosDeviceBasicsType*).

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

## -remarks

To get extended error information, call [GetLastError](https://docs.microsoft.com/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). The following list shows common error values:

- STATUS_BUFFER_TOO_SMALL: The output buffer is not large enough to contain the result.

- STATUS_INSUFFICIENT_RESOURCES: There is insufficient memory.

Provide the version of the POS WinRT API to inform the driver which version of the runtime it is working with. This IOCTL returns the version of the driver in [PosDeviceBasicsType](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posdevicebasicstype), so that you can have the driver version available in the runtime API if you wish to provide it.

