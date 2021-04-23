---
UID: NF:ntddk.PshedUnregisterPlugin
title: PshedUnregisterPlugin function
description: Reserved for system use.
tech.root: whea
ms.date: 08/19/2019
keywords: ["PshedUnregisterPlugin function"]
ms.keywords: PshedUnregisterPlugin
req.header: ntddk.h
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
ms.custom: 19H1
f1_keywords:
 - PshedUnregisterPlugin
 - ntddk/PshedUnregisterPlugin
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntddk.h
api_name:
 - PshedUnregisterPlugin
product:
 - Windows
---

# PshedUnregisterPlugin function


## -description

When registering a V2 plugin (**WHEA_PLUGIN_REGISTRATION_PACKET_V2**) this interface allows the plugin to unregister from the system so the driver can be stopped.

## -parameters

### -param PluginHandle

Specifies the plugin to unload. Use the [PluginHandle](./ns-ntddk-whea_pshed_plugin_registration_packet_v2.md) that the packet contains after registering a V2 plugin.

## -returns

This function returns NTPSHEDAPI VOID.

## -remarks

## -see-also

