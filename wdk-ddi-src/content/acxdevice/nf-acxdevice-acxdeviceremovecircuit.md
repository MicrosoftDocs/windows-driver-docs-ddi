---
UID: NF:acxdevice.AcxDeviceRemoveCircuit
tech.root: audio
title: AcxDeviceRemoveCircuit
ms.date: 01/31/2022
targetos: Windows
description: The AcxDeviceRemoveCircuit function removes the specified audio circuit from an ACX device.
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
 - AcxDeviceRemoveCircuit
f1_keywords:
 - AcxDeviceRemoveCircuit
 - acxdevice/AcxDeviceRemoveCircuit
dev_langs:
 - c++
---

## -description

The **AcxDeviceRemoveCircuit** function removes the specified audio circuit from an ACX device.

## -parameters

### -param Device

The **WDFDEVICE** from which to remove the audio circuit specified by the *Circuit* parameter.

### -param Circuit

The audio circuit to remove from the WDFDEVICE specified by the *Device* parameter.

## -returns

**AcxDeviceRemoveCircuit** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

Use [AcxDeviceAddCircuit](nf-acxdevice-acxdeviceaddcircuit.md) to add an audio circuit to a **WDFDEVICE**.

This function can only be called from the [EVT_WDF_DEVICE_RELEASE_HARDWARE](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware) callback function for this device.

### Example

```cpp
NTSTATUS              status;
WDFDEVICE             Device = NULL;
PUSBA2_DEVICE_CONTEXT devCtx;

// Code to initialize WDFDEVICE...

devCtx = GetDeviceContext(Device);

//
// Unregister filter and delete this audio filter.
//
if (devCtx->RenderCircuitAdded) {
    ASSERT(devCtx->RenderCircuit);
    status = AcxDeviceRemoveCircuit(Device, devCtx->RenderCircuit);

    devCtx->RenderCircuit = NULL;
    devCtx->RenderCircuitAdded = FALSE;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [AcxDeviceAddCircuit](nf-acxdevice-acxdeviceaddcircuit.md)
- [AcxDeviceRemoveCircuitDevice](nf-acxdevice-acxdeviceremovecircuitdevice.md)
- [acxdevice.h header](index.md)
