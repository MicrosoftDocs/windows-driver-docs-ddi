---
UID: NF:acxdevice.AcxDeviceRemoveFactoryCircuit
tech.root: audio
title: AcxDeviceRemoveFactoryCircuit
ms.date: 01/31/2022
targetos: Windows
description: The AcxDeviceRemoveFactoryCircuit function removes a factory circuit for creating audio circuits from a WDFDEVICE.
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
 - AcxDeviceRemoveFactoryCircuit
f1_keywords:
 - AcxDeviceRemoveFactoryCircuit
 - acxdevice/AcxDeviceRemoveFactoryCircuit
dev_langs:
 - c++
---

## -description

The **AcxDeviceRemoveFactoryCircuit** function removes a factory circuit for creating audio circuits from a **WDFDEVICE**.

## -parameters

### -param Device

The **WDFDEVICE** from which the ACX factory circuit will be removed.

### -param Factory

The ACX factory circuit to remove from the **WDFDEVICE** specified by the *Device* parameter.

## -returns

**AcxDeviceRemoveFactoryCircuit** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

Use [AcxDeviceAddFactoryCircuit](nf-acxdevice-acxdeviceaddfactorycircuit.md) to add a factory circuit to a **WDFDEVICE**.

This function can only be called from the [EVT_WDF_DEVICE_RELEASE_HARDWARE](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware) callback function for this device.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

* [AcxDeviceAddFactoryCircuit](nf-acxdevice-acxdeviceaddfactorycircuit.md)
* [AcxDeviceRemoveCircuit](nf-acxdevice-acxdeviceremovecircuit.md)
* [AcxDeviceRemoveCircuitDevice](nf-acxdevice-acxdeviceremovecircuitdevice.md)
* [acxdevice.h header](index.md)

