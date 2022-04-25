---
UID: NF:acxdevice.AcxDeviceGetCurrentDxExitLatency
tech.root: audio
title: AcxDeviceGetCurrentDxExitLatency
ms.date: 01/31/2022
targetos: Windows
description: The AcxDeviceGetCurrentDxExitLatency function gets the current audio device sleep state exit latency value.
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
 - AcxDeviceGetCurrentDxExitLatency
f1_keywords:
 - AcxDeviceGetCurrentDxExitLatency
 - acxdevice/AcxDeviceGetCurrentDxExitLatency
dev_langs:
 - c++
---

## -description

The **AcxDeviceGetCurrentDxExitLatency** function gets the current audio device sleep state exit latency value.

## -parameters

### -param Device

Pointer to the **WDFDEVICE** for which to get the exit latency.

### -param SystemPowerAction

The [system power action](/windows-hardware/drivers/kernel/system-power-actions) for which to get the latency value.

### -param DeviceState

The device [power state](/windows-hardware/drivers/nfc/power-states) for which to get the latency value.

## -returns

**AcxDeviceGetCurrentDxExitLatency** returns the current device exit latency value as defined in the [ACX_DX_EXIT_LATENCY](ne-acxdevice-acx_dx_exit_latency.md) enumeration.

## -remarks

A device has different power states. The D0 power state is when the device is up and running, D1 is when the device is one of the sleep states, and so on. "Dx" refers to any device sleep state.

Audio drivers know when to go in [D3Hot](/windows-hardware/drivers/kernel/device-sleeping-states#d3hot) or [D3Cold](/windows-hardware/drivers/kernel/device-sleeping-states#d3cold-substate) based on the [ACX_DX_EXIT_LATENCY](ne-acxdevice-acx_dx_exit_latency.md) returned by this method.

### Example

```cpp
WDFDEVICE              Device;
WDF_POWER_DEVICE_STATE TargetState;
ACX_DX_EXIT_LATENCY    latency;
POWER_ACTION           powerAction;

// Code to initialize WDFDEVICE and WDF_POWER_DEVICE_STATE...

powerAction = WdfDeviceGetSystemPowerAction(Device);

//
// Get the current exit latency.
//
latency = AcxDeviceGetCurrentDxExitLatency(Device, powerAction, TargetState);
```

## -see-also

* [ACX_DX_EXIT_LATENCY](ne-acxdevice-acx_dx_exit_latency.md)
* [System Power Actions](/windows-hardware/drivers/kernel/system-power-actions)
* [Power states](/windows-hardware/drivers/nfc/power-states)
* [acxdevice.h header](index.md)

READY2GO

EDITCOMPLETE
