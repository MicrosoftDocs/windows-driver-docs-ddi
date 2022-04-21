---
UID: NE:acxdevice._ACX_DX_EXIT_LATENCY
tech.root: audio
title: ACX_DX_EXIT_LATENCY
ms.date: 01/31/2022
targetos: Windows
description: The ACX_DX_EXIT_LATENCY enum defines values that define the ACX device exit latency.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxdevice.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdevice.h
api_name:
 - _ACX_DX_EXIT_LATENCY
 - ACX_DX_EXIT_LATENCY
f1_keywords:
 - _ACX_DX_EXIT_LATENCY
 - acxdevice/_ACX_DX_EXIT_LATENCY
 - ACX_DX_EXIT_LATENCY
 - acxdevice/ACX_DX_EXIT_LATENCY
dev_langs:
 - c++
---

## -description

The **ACX_DX_EXIT_LATENCY** enum defines values that specify an ACX device's sleep state exit latency.

## -enum-fields

### -field AcxDxExitLatencyInstant

The device is powered up, so the device must be able to respond immediately.

### -field AcxDxExitLatencyFast

The system is in S0 and not in connected standby, so it must be fast when powering up. This value corresponds to the [D3Hot](/windows-hardware/drivers/kernel/device-sleeping-states#d3hot) power sub-state.

### -field AcxDxExitLatencyResponsive

The system is entering a sleep state, so the longest exit latency can be tolerated. This value corresponds to the [D3Cold](/windows-hardware/drivers/kernel/device-sleeping-states#d3cold-substate) power sub-state.

## -remarks

A device has different power states. The D0 power state is when the device is up and running, D1 is when the device is one of the sleep states, and so on. "Dx" refers to any device sleep state.

## -see-also

* [AcxDeviceGetCurrentDxExitLatency](nf-acxdevice-acxdevicegetcurrentdxexitlatency.md)
* [System Power States](/windows-hardware/drivers/kernel/system-power-states)
* [PC_EXIT_LATENCY](../portcls/ne-portcls-_pc_exit_latency.md)
* [acxdevice.h header](index.md)

READY2GO

EDITCOMPLETE
