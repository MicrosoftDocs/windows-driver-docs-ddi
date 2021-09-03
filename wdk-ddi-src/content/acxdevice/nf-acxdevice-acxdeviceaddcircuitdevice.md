---
UID: NF:acxdevice.AcxDeviceAddCircuitDevice
tech.root: audio
title: AcxDeviceAddCircuitDevice
ms.date: 09/02/2021
targetos: Windows
description: The AcxDeviceAddCircuitDevice function adds an ACX circuit device to a specified parent device representing an audio path.
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

## -see-also

[AcxDeviceAddCircuit](nf-acxdevice-acxdeviceaddcircuit.md)

[AcxDeviceRemoveCircuitDevice](nf-acxdevice-acxdeviceremovecircuitdevice.md)
