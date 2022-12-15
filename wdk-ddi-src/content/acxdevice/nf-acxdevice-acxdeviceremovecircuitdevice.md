---
UID: NF:acxdevice.AcxDeviceRemoveCircuitDevice
tech.root: audio
title: AcxDeviceRemoveCircuitDevice
ms.date: 12/15/2022
targetos: Windows
description: The AcxDeviceRemoveCircuitDevice function removes an ACX circuit device from a specified parent device.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdevice.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - AcxDeviceRemoveCircuitDevice
f1_keywords:
 - AcxDeviceRemoveCircuitDevice
 - acxdevice/AcxDeviceRemoveCircuitDevice
dev_langs:
 - c++
---

## -description

The **AcxDeviceRemoveCircuitDevice** function removes an ACX circuit device from a specified parent device.

## -parameters

### -param ParentDevice

The parent **WDFDEVICE** from which to remove the ACX circuit device.

### -param Device

The **WDFDEVICE** representing the circuit device to remove from the parent device.

## -returns

**AcxDeviceRemoveCircuitDevice** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

Audio drivers use this function to remove an existing audio endpoint.

This function can be called at any time during the driver's life cycle. Plug and Play takes care to serialize the removal of the device, and the associated circuits, in relation to other Plug and Play activities on the parent and siblings devices.

### Example

```cpp
NTSTATUS status;
WDFDEVICE Device;
WDFDEVICE child;

// Code to initialize WDFDEVICE objects...

// Remove the child device.
status = AcxDeviceRemoveCircuitDevice(Device, child);

if (!NT_SUCCESS(status)) 
{
    ASSERT(FALSE);
    goto exit;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [AcxDeviceRemoveCircuit](nf-acxdevice-acxdeviceremovecircuit.md)
- [acxdevice.h header](index.md)
