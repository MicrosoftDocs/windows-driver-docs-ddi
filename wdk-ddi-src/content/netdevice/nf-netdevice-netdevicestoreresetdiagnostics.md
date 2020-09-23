---
UID: NF:netdevice.NetDeviceStoreResetDiagnostics
title: NetDeviceStoreResetDiagnostics
ms.topic: language-reference
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: The NetDeviceStoreResetDiagnostics function stores client driver collected reset diagnostics into the NetAdapterCx framework.
keywords: ["NetDeviceStoreResetDiagnostics function"]
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
 - NetDeviceStoreResetDiagnostics
f1_keywords:
 - netdevice/NetDeviceStoreResetDiagnostics
dev_langs:
 - c++
---

## -description

The **NetDeviceStoreResetDiagnostics** function stores client driver collected reset diagnostics into the NetAdapterCx framework.

## -parameters

### -param Device

[in] The WDFDEVICE object the client driver previously created with a call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param ResetDiagnosticsSize

[in] The size in bytes of the **ResetDiagnosticsBuffer**. The maximum size of reset diagnostics the framework accepts is 1 MB.

### -param ResetDiagnosticsBuffer

[in] A pointer to the data buffer that holds the reset diagnostics data. The data buffer can come from either paged or non-paged pool.

## -remarks

The only valid scenario to invoke the **NetDeviceStoreResetDiagnostics** function is in a client driver's [*EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS*](nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback. The client driver must call **NetDeviceStoreResetDiagnostics** at PASSIVE_LEVEL

To learn how to correctly use the **NetDeviceStoreResetDiagnostics** function, see [Implement *EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS*](/windows-hardware/drivers/netcx/platform-level-device-reset/#implement-EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS).

## -see-also

[Recovering an unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[*EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS*](nc-netdevice-evt_net_device_collect_reset_diagnostics.md)
