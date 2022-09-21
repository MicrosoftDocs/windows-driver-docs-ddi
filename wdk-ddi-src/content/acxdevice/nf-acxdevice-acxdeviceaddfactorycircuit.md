---
UID: NF:acxdevice.AcxDeviceAddFactoryCircuit
tech.root: audio
title: AcxDeviceAddFactoryCircuit
ms.date: 01/31/2022
targetos: Windows
description: The AcxDeviceAddFactoryCircuit function adds a factory circuit to a WDFDEVICE for creating audio circuits.
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
 - AcxDeviceAddFactoryCircuit
f1_keywords:
 - AcxDeviceAddFactoryCircuit
 - acxdevice/AcxDeviceAddFactoryCircuit
dev_langs:
 - c++
---

## -description

The **AcxDeviceAddFactoryCircuit** function adds a factory circuit to a **WDFDEVICE** for creating audio circuits.

## -parameters

### -param Device

A **WDFDEVICE** to which the ACX factory circuit will be added.

### -param Factory

The ACX factory circuit to add to the **WDFDEVICE** specified by the *Device* parameter.

## -returns

**AcxDeviceAddFactoryCircuit** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

An ACX driver may create one or more circuits in the following scenarios:

* At initialization time
* At run time, as side effect of an external event, such as detecting a new audio component
* Because it registered itself with ACX as circuit factory. The ACX framework uses the registered factory to ask the driver to create a new circuit.

Use [AcxDeviceRemoveFactoryCircuit](nf-acxdevice-acxdeviceremovefactorycircuit.md) to remove a factory circuit from a **WDFDEVICE**.

This function can only be called from the [EVT_WDF_DEVICE_PREPARE_HARDWARE](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware) callback function for this device.

### Example

```cpp
WDFDEVICE                Device;
NTSTATUS                 status;
PCAPTURE_DEVICE_CONTEXT  devCtx;

// Code to initialize WDFDEVICE...

//
// Add control circuit to child's list.
//
status = AcxDeviceAddFactoryCircuit(Device, devCtx->CtrlCircuit);

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

* [AcxDeviceRemoveFactoryCircuit](nf-acxdevice-acxdeviceremovefactorycircuit.md)
* [acxdevice.h header](index.md)

