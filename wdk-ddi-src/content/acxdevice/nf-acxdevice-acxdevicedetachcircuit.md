---
UID: NF:acxdevice.AcxDeviceDetachCircuit
tech.root: audio
title: AcxDeviceDetachCircuit
ms.date: 09/02/2021
targetos: Windows
description: The AcxDeviceDetachCircuit function detaches an audio circuit from a WDFDEVICE prior to removal.
prerelease: true
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

## -remarks

## -see-also

[AcxDeviceRemoveCircuit](nf-acxdevice-acxdeviceremovecircuit.md)

[AcxDeviceRemoveCircuitDevice](nf-acxdevice-acxdeviceremovecircuitdevice.md)
