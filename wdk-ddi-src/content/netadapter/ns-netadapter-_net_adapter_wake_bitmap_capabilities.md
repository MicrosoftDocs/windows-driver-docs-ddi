---
UID: NS:netadapter._NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
title: NET_ADAPTER_WAKE_BITMAP_CAPABILITIES (netadapter.h)
description: The NET_ADAPTER_WAKE_BITMAP_CAPABILITIES structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a bitmap pattern.
tech.root: netvista
ms.date: 10/24/2019
keywords: ["NET_ADAPTER_WAKE_BITMAP_CAPABILITIES structure"]
ms.keywords: NET_ADAPTER_WAKE_BITMAP_CAPABILITIES, NET_ADAPTER_WAKE_BITMAP_CAPABILITIES,
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
 - netadapter/_NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
 - NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
 - netadapter/NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - _NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
 - NET_ADAPTER_WAKE_BITMAP_CAPABILITIES
product:
 - Windows
---

# NET_ADAPTER_WAKE_BITMAP_CAPABILITIES structure


## -description

The **NET_ADAPTER_WAKE_BITMAP_CAPABILITIES** structure describes a net adapter's wake on LAN (WoL) capabilities for waking from a bitmap pattern.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field BitmapPattern

A boolean value that describes if the net adapter is capable of waking from a bitmap pattern.

### -field MaximumPatternCount

The maximum number of bitmap patterns that the hardware supports.

### -field MaximumPatternSize

The maximum size, in bytes, for the bitmap patterns that the hardware supports.

## -remarks

Call [**NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_bitmap_capabilities_init.md) to initialize this structure, then call [**NetAdapterWakeSetBitmapCapabilities**](../netadapter/nf-netadapter-netadapterwakesetbitmapcapabilities.md) to set the net adapter's bitmap pattern WoL capabilities. Client drivers typically call **NetAdapterWakeSetBitmapCapabilities** when starting a net adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_BITMAP_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_bitmap_capabilities_init.md)

[**NetAdapterWakeSetBitmapCapabilities**](../netadapter/nf-netadapter-netadapterwakesetbitmapcapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)

