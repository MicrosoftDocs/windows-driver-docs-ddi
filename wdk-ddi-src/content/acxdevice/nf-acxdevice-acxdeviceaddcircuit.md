---
UID: NF:acxdevice.AcxDeviceAddCircuit
tech.root: audio
title: AcxDeviceAddCircuit
ms.date: 12/15/2022
targetos: Windows
description: The AcxDeviceAddCircuit function adds an ACX circuit to a WDFDEVICE to create an audio endpoint.
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
 - AcxDeviceAddCircuit
f1_keywords:
 - AcxDeviceAddCircuit
 - acxdevice/AcxDeviceAddCircuit
dev_langs:
 - c++
---

## -description

The **AcxDeviceAddCircuit** function adds an ACX circuit to a **WDFDEVICE** to create an audio endpoint.

## -parameters

### -param Device

A **WDFDEVICE** representing the device to which the circuit will be added.

### -param Circuit

The circuit to add to the *Device*.

## -returns

**AcxDeviceAddCircuit** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

The audio circuit is the core building block of ACX. An audio driver creates one or more ACX circuit objects to represent a partial or complete audio data and control path. ACX assembles these ACX circuit objects together to create a complete audio path which represents an audio endpoint.

This function can only be called from the [EVT_WDF_DEVICE_PREPARE_HARDWARE](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware) callback function for this device.

### Example

```cpp
WDFDEVICE             Device;
NTSTATUS              status;
PCODEC_DEVICE_CONTEXT devCtx;

// Code to initialize the WDFDEVICE...

devCtx = GetCodecDeviceContext(Device);
ASSERT(devCtx != NULL);

//
// Add static circuit to device's list.
//
ASSERT(devCtx->Render);
status = AcxDeviceAddCircuit(Device, devCtx->Render);

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

- [AcxDeviceAddCircuitDevice](nf-acxdevice-acxdeviceaddcircuitdevice.md)
- [AcxDeviceDetachCircuit](nf-acxdevice-acxdevicedetachcircuit.md)
- [AcxDeviceRemoveCircuit](nf-acxdevice-acxdeviceremovecircuit.md)
- [acxdevice.h header](index.md)
