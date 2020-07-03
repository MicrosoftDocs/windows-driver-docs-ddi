---
UID: NC:netdevice.EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS
title: EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS (netdevice.h)
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: Implement this optional callback to collect diagnostics from hardware device and report it to the framework before device reset.
keywords: ["EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS callback function"]
req.assembly:
req.construct-type: function
req.ddi-compliance:
req.dll:
req.header: netdevice.h
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
 - netdevice.h
api_name:
 - EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS
f1_keywords:
 - netdevice/EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS
dev_langs:
 - c++
---

# EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS callback function

## -description

Implement this optional callback to collect diagnostics from hardware device and report it to the framework before device reset happens.

## -prototype

```cpp
// Declaration
EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS EvtNetDeviceCollectResetDiagnostics;

// Definition
void EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS
(
    WDFDEVICE Device
)
{...}
```

## -parameters

### -param Device:

The WDFDEVICE object that the client driver previously obtained with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -remarks
If provided, the framework (NetAdapterCx) invokes **EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS** callback to collect reset diagnostics in the process of platform-level device reset (PLDR).
NetAdapterCx always invokes **EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS** callback at PASSIVE_LEVEL.

This callback is defined as a field of the [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES**](../netdevice/ns-netdevice-net_device_reset_diagnostics_capabilities.md) data structure. Register your implementation of this callback function by calling [**NetDeviceInitSetResetDiagnosticsCapabilitites**](../netdevice/nf-netdevice-netdeviceinitsetresetdiagnosticscapabilitites.md).

Since invokding PLDR using [**NetDeviceRequestReset**](../netdevice/nf-netdevice-netdevicerequestreset.md) is non-blocking and NetAdapterCx guarantees that **EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS** is invoked in a dedicated thread, client driver should synchronize the handling of collecting diagnotics from device with other ongoing control job on the device in order to avoid dead lock.
Client driver should complete **EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS** callback as soon as possible, and should not use this callback to deliberately delay device reset.
For more info, see [Recovering unresponsive NIC with platform-level device reset](/windows-hardware/drivers/netcx/platform-level-device-reset).

## -see-also
