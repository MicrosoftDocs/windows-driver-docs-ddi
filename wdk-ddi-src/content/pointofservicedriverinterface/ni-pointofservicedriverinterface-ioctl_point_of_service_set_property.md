---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_SET_PROPERTY
title: IOCTL_POINT_OF_SERVICE_SET_PROPERTY (pointofservicedriverinterface.h)
description: This I/O control function sets the specified property on the device.
old-location: pos\ioctl_point_of_service_set_property.htm
tech.root: pos
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_SET_PROPERTY IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_SET_PROPERTY, IOCTL_POINT_OF_SERVICE_SET_PROPERTY control, IOCTL_POINT_OF_SERVICE_SET_PROPERTY control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_SET_PROPERTY, pos.ioctl_point_of_service_set_property
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
 - IOCTL_POINT_OF_SERVICE_SET_PROPERTY
 - pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_SET_PROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - IOCTL_POINT_OF_SERVICE_SET_PROPERTY
---

# IOCTL_POINT_OF_SERVICE_SET_PROPERTY IOCTL


## -description

This I/O control function sets the specified property on the device.

## -ioctlparameters

### -input-buffer

[PosPropertyId](./ne-pointofservicedriverinterface-_pospropertyid.md) of the property to set followed by the value of the property. The encoding for the type follows the property ID in the byte stream.

### -input-buffer-length

Set to sizeof(*PosPropertyId*) + the size of the property value.

### -output-buffer

Not used with this operation; set to **NULL**.

### -output-buffer-length

Not used with this operation; set to **0** (zero).

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

## -remarks

To get extended error information, call [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). The following is a common error value (other return values may be returned as defined by your property callback implementation):

- STATUS_ACCESS_DENIED: The device is currently claimed by another client.

The client must successfully call [IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE](./ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device.md) before using this IOCTL.
