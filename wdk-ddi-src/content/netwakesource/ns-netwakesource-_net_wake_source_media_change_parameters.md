---
UID: NS:netwakesource._NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS
title: NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS (netwakesource.h)
author: windows-driver-content
description: The NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS structure contains parameters for a media change wake-on-LAN (WoL) wake source.
tech.root: netvista
ms.assetid: de7b5a2a-dc88-4b27-8896-7682e8dce72a
ms.author: windowsdriverdev
ms.date: 10/07/2019
ms.topic: struct
f1_keywords:
 - "netwakesource/NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS"
ms.keywords: NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS, NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS, 
req.header: netwakesource.h
req.include-header:
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
req.typenames: NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - netwakesource.h
api_name: 
 - NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS structure

## -description

The **NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS** structure contains parameters for a media change wake-on-LAN (WoL) wake source.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field MediaConnect

A boolean value that specifies if the net adapter generated the wake-up event because it connected to the network media.
 
### -field MediaDisconnect

A boolean value that specifies if the net adapter generated the wake-up event because it disconnected from the network media. 

## -remarks

Call [**NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT**](../netwakesource/nf-netwakesource-net_wake_source_media_change_parameters_init.md) to initialize this structure and fill in its **Size** field. After calling **NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT**, call [**NetWakeSourceGetMediaChangeParameters**](../netwakesource/nf-netwakesource-netwakesourcegetmediachangeparameters.md) to fill in the other members of the structure.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_MEDIA_CHANGE_PARAMETERS_INIT**](../netwakesource/nf-netwakesource-net_wake_source_media_change_parameters_init.md)

[**NetWakeSourceGetMediaChangeParameters**](../netwakesource/nf-netwakesource-netwakesourcegetmediachangeparameters.md)