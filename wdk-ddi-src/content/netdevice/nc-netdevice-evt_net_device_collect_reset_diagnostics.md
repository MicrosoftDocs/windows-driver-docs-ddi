---
UID: NC:netdevice.EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS
title: EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS (netdevice.h)
ms.topic: language-reference
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: Implement EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS to collect diagnostics from a failed hardware device and report it to the framework during the device reset and recovery process.
keywords: ["EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS callback function"]
req.assembly:
req.construct-type: function
req.ddi-compliance:
req.dll:
req.header: netadaptercx.h
req.idl:
req.include-header: netadaptercx.h
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

Implement this optional callback to collect diagnostics from a failed hardware device and report it to the NetAdapterCx framework during the device reset and recovery process.

## -parameters

### -param Device

[_In_] The WDFDEVICE object that the client driver previously obtained with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -remarks

If provided, the NetAdapterCx framework invokes the *EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS* callback to collect reset diagnostics during the reset and recovery process. The framework always invokes this callback at PASSIVE_LEVEL.

The ***EvtNetDeviceCollectResetDiagnostics*** field of the [**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md) data structure refers to this callback.

To learn how to correctly implement this callback and for more information about the framework's synchronization guarantee, see [Implement *EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS*](/windows-hardware/drivers/netcx/platform-level-device-reset/#implement-EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS).

## -see-also

[Recovering an unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md)
