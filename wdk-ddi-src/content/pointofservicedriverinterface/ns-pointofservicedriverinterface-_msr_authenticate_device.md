---
UID: NS:pointofservicedriverinterface._MSR_AUTHENTICATE_DEVICE
title: _MSR_AUTHENTICATE_DEVICE (pointofservicedriverinterface.h)
description: This structure provides the authentication information used to authenticate a device.
old-location: pos\msr_authenticate_device.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["MSR_AUTHENTICATE_DEVICE structure"]
ms.keywords: "*PMSR_AUTHENTICATE_DEVICE, MSR_AUTHENTICATE_DEVICE, MSR_AUTHENTICATE_DEVICE structure, PMSR_AUTHENTICATE_DEVICE, PMSR_AUTHENTICATE_DEVICE structure pointer, _MSR_AUTHENTICATE_DEVICE, pointofservicedriverinterface/MSR_AUTHENTICATE_DEVICE, pointofservicedriverinterface/PMSR_AUTHENTICATE_DEVICE, pos.msr_authenticate_device"
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
req.typenames: MSR_AUTHENTICATE_DEVICE, *PMSR_AUTHENTICATE_DEVICE
f1_keywords:
 - _MSR_AUTHENTICATE_DEVICE
 - pointofservicedriverinterface/_MSR_AUTHENTICATE_DEVICE
 - PMSR_AUTHENTICATE_DEVICE
 - pointofservicedriverinterface/PMSR_AUTHENTICATE_DEVICE
 - MSR_AUTHENTICATE_DEVICE
 - pointofservicedriverinterface/MSR_AUTHENTICATE_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - _MSR_AUTHENTICATE_DEVICE
 - PMSR_AUTHENTICATE_DEVICE
 - MSR_AUTHENTICATE_DEVICE
---

# _MSR_AUTHENTICATE_DEVICE structure


## -description

This structure provides the authentication information used to authenticate a device.

## -struct-fields

### -field Size

If the optional **SessionId** is present, this will include the size of **SessionId[MSR_SESSION_ID_SIZE]**

### -field Challenge1

The challenge token.

### -field SessionId

The session ID. This is primarily used to identify each transaction so that you can prevent errors such as processing the same transaction twice.

## -see-also

<a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_msr_authenticate_device">IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE</a>

