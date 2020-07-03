---
UID: NS:netdevice._NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
title: NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
author: windows-driver-content
ms.topic: language-reference
ms.author: windowsdriverdev
ms.date: 07/02/2020
ms.custom: Fe
targetos: Windows
description: The NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES structure describes the client driver's capabilities to collect diagnostics during device reset.
keywords: ["EVT_NET_DEVICE_COLLECT_RESET_DIAGNOSTICS callback function"]
req.construct-type: structure
req.ddi-compliance:
req.dll:
req.header: netdevice.h
req.include-header:
req.kmdf-ver:
req.lib:
req.max-support:
req.redist:
req.target-min-winverclnt:
req.target-min-winversvr:
req.target-type:
req.typenames: NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
req.umdf-ver:
req.unicode-ansi:
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netdevice.h
api_name:
 - _NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
 - NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
f1_keywords:
 - netdevice/_NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
 - netdevice/NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES
dev_langs:
 - c++
---

## -description

The NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES structure describes the client driver's capabilities to collect diagnostics during device reset.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field ResetDiagnosticsGuid

A global unique identifier (GUID) associated with the reset diagnostics data within the full kernel dump captured during device reset.

### -field EvtNetDeviceCollectResetDiagnostics

A pointer to the client driver's implementation of the [**EvtNetDeviceCollectResetDiagnostics**](../netdevice/nc-netdevice-evt_net_device_collect_reset_diagnostics.md) callback function for collecting reset diagnostics from hardware device.
This member is optional. Framework will not ask the client driver to collect reset diagnostics when this callback is `nullptr`.

## -remarks

Call [**NET_DEVICE_RESET_DIAGNOSTICS_CAPABILITIES_INIT**](../netdevice/nf-netdevice-net_device_reset_diagnostics_capabilities_init.md) method to initialize this structure.
For more information about how framework collecting reset diagnostics during device reset and recovering, see [Recovering unresponsive NIC with platform-level device reset](/windows-hardware/drivers/netcx/platform-level-device-reset).

## -see-also

