---
UID: NS:netwakesourcelist._NET_WAKE_SOURCE_LIST
title: NET_WAKE_SOURCE_LIST (netwakesourcelist.h)
author: windows-driver-content
description: The NET_WAKE_SOURCE_LIST structure represents a list of wake-on-LAN (WoL) sources for a net adapter.
tech.root: netvista
ms.assetid: f43e14e4-9aa0-4401-9e9c-7a2a36fd3899
ms.author: windowsdriverdev
ms.date: 10/07/2019
keywords: ["NET_WAKE_SOURCE_LIST structure"]
ms.keywords: NET_WAKE_SOURCE_LIST, NET_WAKE_SOURCE_LIST,
req.header: netwakesourcelist.h
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
req.typenames: NET_WAKE_SOURCE_LIST
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_WAKE_SOURCE_LIST
 - netwakesourcelist/_NET_WAKE_SOURCE_LIST
 - NET_WAKE_SOURCE_LIST
 - netwakesourcelist/NET_WAKE_SOURCE_LIST
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netwakesourcelist.h
api_name:
 - NET_WAKE_SOURCE_LIST
product:
 - Windows
---

# NET_WAKE_SOURCE_LIST structure


## -description

The **NET_WAKE_SOURCE_LIST** structure represents a list of wake-on-LAN (WoL) sources for a net adapter.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Reserved

 
Reserved. Client drivers must not read or write to this value directly.

## -remarks

Call [**NET_WAKE_SOURCE_LIST_INIT**](../netwakesourcelist/nf-netwakesourcelist-net_wake_source_list_init.md) to initialize this structure, then call [**NetDeviceGetWakeSourceList**](../netwakesourcelist/nf-netwakesourcelist-netdevicegetwakesourcelist.md) to get the list of wake sources from this net adapter. After you obtain the list, call [**NetWakeSourceListGetCount**](../netwakesourcelist/nf-netwakesourcelist-netwakesourcelistgetcount.md) with this structure to get the number of NETWAKESOURCE objects that represents the wake sources, then loop over the objects and call [**NetWakeSourceListGetElement**](../netwakesourcelist/nf-netwakesourcelist-netwakesourcelistgetelement.md) to retrieve each one. Once you have obtained a NETWAKESOURCE object, call [**NetWakeSourceGetType**](../netwakesource/nf-netwakesource-netwakesourcegettype.md) to get the type of that wake source so you can call the appropriate function to get the wake source's parameters.

The client driver must only call wake source-related functions during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

For a code sample of working with NETWAKESOURCE objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_LIST_INIT**](../netwakesourcelist/nf-netwakesourcelist-net_wake_source_list_init.md)

[**NetDeviceGetWakeSourceList**](../netwakesourcelist/nf-netwakesourcelist-netdevicegetwakesourcelist.md)

[**NetWakeSourceListGetCount**](../netwakesourcelist/nf-netwakesourcelist-netwakesourcelistgetcount.md)

[**NetWakeSourceListGetElement**](../netwakesourcelist/nf-netwakesourcelist-netwakesourcelistgetelement.md)

[**NetWakeSourceGetType**](../netwakesource/nf-netwakesource-netwakesourcegettype.md)

