---
UID: NF:portcls.IPort.GetDeviceProperty
title: IPort::GetDeviceProperty (portcls.h)
description: The GetDeviceProperty method provides simplified access to device properties that are contained in the registry for Plug and Play devices.
tech.root: audio
ms.assetid: 7ca86c00-624a-4c09-9f20-8dc11dd6a1bc
ms.date: 10/31/2018
keywords: ["IPort::GetDeviceProperty"]
f1_keywords:
 - "portcls/IPort.GetDeviceProperty"
 - "IPort.GetDeviceProperty"
ms.keywords: IPort::GetDeviceProperty, GetDeviceProperty, IPort.GetDeviceProperty, IPort::GetDeviceProperty, IPort.GetDeviceProperty
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IPort.GetDeviceProperty
product: 
 - Windows
targetos: Windows

---

# IPort::GetDeviceProperty


## -description

The GetDeviceProperty method provides simplified access to device properties that are contained in the registry for Plug and Play devices.

## -parameters

### -param DeviceProperty
Identifies the particular device property that the caller is requesting. The valid values for this parameter are the same as those that are defined for the IoGetDeviceProperty call's DeviceProperty parameter.

### -param BufferLength
Specifies the length in bytes of the buffer that is to receive the requested information.

### -param PropertyBuffer
Pointer to the property buffer. This parameter points to a caller-allocated buffer into which the method writes the requested property information. The buffer must be large enough to contain the number of bytes specified in BufferLength.

### -param ResultLength
Output pointer to the length of the returned data. This parameter points to a caller-allocated ULONG variable into which the method writes a count specifying the number of bytes actually written to the PropertyBuffer buffer. If the buffer is too small to contain the information, however, the method instead outputs the required buffer size.


## -returns
This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. If the property buffer provided by the caller is too small, the method will return STATUS_BUFFER_TOO_SMALL and output the needed size in ReturnLength.

## -remarks

This method retrieves the audio adapter's device properties. It is similar in operation to the PcGetDeviceProperty function, except that it automatically retrieves the device properties of the audio adapter rather than requiring a device object to explicitly specify a target device.

## -see-also

[IPort](nn-portcls-iport.md)
