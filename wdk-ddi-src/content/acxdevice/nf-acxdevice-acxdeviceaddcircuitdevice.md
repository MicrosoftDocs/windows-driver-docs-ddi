---
UID: NF:acxdevice.AcxDeviceAddCircuitDevice
tech.root: audio
title: AcxDeviceAddCircuitDevice
ms.date: 01/31/2022
targetos: Windows
description: The AcxDeviceAddCircuitDevice function adds an ACX circuit device to a specified parent device representing an audio path.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdevice.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxdevice.h
api_name:
 - AcxDeviceAddCircuitDevice
f1_keywords:
 - AcxDeviceAddCircuitDevice
 - acxdevice/AcxDeviceAddCircuitDevice
dev_langs:
 - c++
---

## -description

The **AcxDeviceAddCircuitDevice** function adds an ACX circuit device to a specified parent device representing an audio path.

## -parameters

### -param ParentDevice

A **WDFDEVICE** representing the parent to which the circuit device will be added.

### -param Device

A **WDFDEVICE** representing the circuit device to add to the parent device.

## -returns

**AcxDeviceAddCircuitDevice** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

Audio drivers use this function to enumerate a new audio endpoint.

This function can be called at any time during the driver's life cycle. Plug and Play serializes the enumeration of the device, and the associated circuits, in relation to other Plug and Play activities on the parent and siblings devices.

### Example

```cpp
WDFDEVICE Device;
WDFDEVICE renderDevice = NULL;
NTSTATUS  status;

// Code to initialize the WDFDEVICE...

// Code to create the WDFDEVICE renderDevice...

//
// Add circuit to device's dynamic circuit device list.
//
status = AcxDeviceAddCircuitDevice(Device, renderDevice);
if (!NT_SUCCESS(status)) 
{
    ASSERT(FALSE);
    goto exit;
}
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

* [AcxDeviceAddCircuit](nf-acxdevice-acxdeviceaddcircuit.md)
* [AcxDeviceRemoveCircuitDevice](nf-acxdevice-acxdeviceremovecircuitdevice.md)
* [acxdevice.h header](index.md)

