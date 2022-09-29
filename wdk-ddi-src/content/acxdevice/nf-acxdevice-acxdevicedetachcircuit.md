---
UID: NF:acxdevice.AcxDeviceDetachCircuit
tech.root: audio
title: AcxDeviceDetachCircuit
ms.date: 01/31/2022
targetos: Windows
description: The AcxDeviceDetachCircuit function detaches an audio circuit from a WDFDEVICE prior to removal.
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
 - AcxDeviceDetachCircuit
f1_keywords:
 - AcxDeviceDetachCircuit
 - acxdevice/AcxDeviceDetachCircuit
dev_langs:
 - c++
---

## -description

The **AcxDeviceDetachCircuit** function detaches an audio circuit from a **WDFDEVICE** prior to removal.

## -parameters

### -param Device

The **WDFDEVICE** from which to detach the audio circuit specified by the *Circuit* parameter.

### -param Circuit

The audio circuit to remove from the **WDFDEVICE** specified by the *Device* parameter.

## -returns

**AcxDeviceDetachCircuit** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

This function can only be called from the [EVT_WDF_DEVICE_RELEASE_HARDWARE](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware) callback function for this device.

**AcxDeviceDetachCircuit** detaches the circuit from the device. The caller is responsible for deleting the **ACXCIRCUIT** object.

## -remarks

### Example

```cpp
WDFDEVICE                    Device;
NTSTATUS                     status;
PCODEC_RENDER_DEVICE_CONTEXT renderDevCtx = NULL;

// Code to initialize WDFDEVICE...

renderDevCtx = GetRenderDeviceContext(Device);

ASSERT(renderDevCtx->Circuit);
status = AcxDeviceDetachCircuit(Device, renderDevCtx->Circuit);

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

* [AcxDeviceRemoveCircuit](nf-acxdevice-acxdeviceremovecircuit.md)
* [AcxDeviceRemoveCircuitDevice](nf-acxdevice-acxdeviceremovecircuitdevice.md)
* [acxdevice.h header](index.md)

