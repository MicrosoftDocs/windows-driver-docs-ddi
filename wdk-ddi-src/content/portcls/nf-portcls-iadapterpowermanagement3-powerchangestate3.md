---
UID: NF:portcls.IAdapterPowerManagement3.PowerChangeState3
title: IAdapterPowerManagement3::PowerChangeState3 (portcls.h)
description: PortCls calls the PowerChangeState3 method to request a change to the new power state. This request is passed on to the adapter driver.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IAdapterPowerManagement3::PowerChangeState3"]
ms.keywords: IAdapterPowerManagement3::PowerChangeState3, PowerChangeState3, IAdapterPowerManagement3.PowerChangeState3, IAdapterPowerManagement3::PowerChangeState3, IAdapterPowerManagement3.PowerChangeState3
req.header: portcls.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IAdapterPowerManagement3::PowerChangeState3
 - portcls/IAdapterPowerManagement3::PowerChangeState3
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IAdapterPowerManagement3::PowerChangeState3
product:
 - Windows
---

# IAdapterPowerManagement3::PowerChangeState3


## -description

PortCls calls the PowerChangeState3 method to request a change to the new power state. This request is passed on to the adapter driver.

## -parameters

### -param NewDeviceState

The new power state that Portcls has requested for the device. This parameter is an enumeration of type DEVICE_POWER_STATE.

### -param NewSystemState

The new power state that Portcls has requested for the system. This parameter is an enumeration of type SYSTEM_POWER_STATE.

### -param D3ExitLatency

The acceptable exit latency for the state into which the device is put when the device comes out of PowerDeviceD3. This parameter is an enumeration of type PC_EXIT_LATENCY.

## -remarks

If the device is not going into its new state from PowerDeviceD3, then D3ExitLatency is set to PcExitLatencyInstant. For more information about the possible values for D3ExitLatency, see [D3ExitLatencyChanged](nf-portcls-iadapterpowermanagement3-d3exitlatencychanged.md).

## -see-also

[IAdapterPowerManagement3](nn-portcls-iadapterpowermanagement3.md)

