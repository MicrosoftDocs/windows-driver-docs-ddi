---
UID: NF:netdevice.NetDeviceInitSetResetCapabilities
title: NetDeviceInitSetResetCapabilities
ms.topic: language-reference
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
keywords: ["NetDeviceInitSetResetCapabilities"]
description: The NetDeviceInitSetResetCapabilities function registers a client driver's NET_DEVICE_RESET_CAPABILITIES to the framework.
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
 - NetDeviceInitSetResetCapabilities
f1_keywords:
 - netdevice/NetDeviceInitSetResetCapabilities
dev_langs:
 - c++
---

## -description

The **NetDeviceInitSetResetCapabilities** function registers a client driver's [**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md) to the NetAdapterCx framework.

## -parameters

### -param DeviceInit

[_Inout_] A pointer to a **WDFDEVICE_INIT** object that the client driver received in its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback.

### -param ResetDiagnosticsCapabilities

[_In_] A pointer to a client driver allocated and initialized [**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md) structure.

## -remarks

A client driver typically calls the **NetDeviceInitSetResetCapabilities** function in its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) callback.

Before calling this function, the client driver must initialize [**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md) by calling the [**NET_DEVICE_RESET_CAPABILITIES_INIT**](nf-netdevice-net_device_reset_capabilities_init.md) function.

## -see-also

[Recovering an unresponsive NIC with NetAdapterCx PLDR](/windows-hardware/drivers/netcx/platform-level-device-reset/)

[*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md)

[**NET_DEVICE_RESET_CAPABILITIES**](ns-netdevice-net_device_reset_capabilities.md)

[**NET_DEVICE_RESET_CAPABILITIES_INIT**](nf-netdevice-net_device_reset_capabilities_init.md)
