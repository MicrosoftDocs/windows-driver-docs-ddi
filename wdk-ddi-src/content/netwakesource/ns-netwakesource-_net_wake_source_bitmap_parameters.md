---
UID: NS:netwakesource._NET_WAKE_SOURCE_BITMAP_PARAMETERS
title: NET_WAKE_SOURCE_BITMAP_PARAMETERS (netwakesource.h)
author: windows-driver-content
description: The NET_WAKE_SOURCE_BITMAP_PARAMETERS structure contains parameters for a wake-on-LAN (WoL) bitmap pattern wake source.
tech.root: netvista
ms.assetid: 2ebc685c-02ef-4640-955f-17b032f4b46a
ms.author: windowsdriverdev
ms.date: 10/07/2019
keywords: ["NET_WAKE_SOURCE_BITMAP_PARAMETERS structure"]
ms.keywords: NET_WAKE_SOURCE_BITMAP_PARAMETERS, NET_WAKE_SOURCE_BITMAP_PARAMETERS,
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
req.typenames: NET_WAKE_SOURCE_BITMAP_PARAMETERS
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_WAKE_SOURCE_BITMAP_PARAMETERS
 - netwakesource/_NET_WAKE_SOURCE_BITMAP_PARAMETERS
 - NET_WAKE_SOURCE_BITMAP_PARAMETERS
 - netwakesource/NET_WAKE_SOURCE_BITMAP_PARAMETERS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netwakesource.h
api_name:
 - NET_WAKE_SOURCE_BITMAP_PARAMETERS
product:
 - Windows
---

# NET_WAKE_SOURCE_BITMAP_PARAMETERS structure


## -description

The **NET_WAKE_SOURCE_BITMAP_PARAMETERS** structure contains parameters for a wake-on-LAN (WoL) bitmap pattern wake source.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field Id

The identifier for this wake source.

### -field Pattern

A sequence of bytes that contains a pattern against which to compare bytes in an incoming packet.

### -field PatternSize

The size of the bitmap pattern, in bytes.

### -field Mask

A mask that specifies which bytes in incoming packets should be matched against the bitmap pattern. Each bit in the bitmask corresponds to a byte in the pattern. If a bit is zero, the corresponding byte in the incoming packet should not be pattern-matched. If the bit is one, the network adapter compares the byte in the incoming packet with the byte specified in the pattern.

### -field MaskSize

The size of the mask, in bytes.

## -remarks

Call [**NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT**](../netwakesource/nf-netwakesource-net_wake_source_bitmap_parameters_init.md) to initialize this structure and fill in its **Size** field. After calling **NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT**, call [**NetWakeSourceGetBitmapParameters**](../netwakesource/nf-netwakesource-netwakesourcegetbitmapparameters.md) to fill in the other members of the structure.

An upper-layer driver can specify a generic WOL pattern with the **Pattern** member. A bitmap pattern is specified as a sequence of bytes and a mask bitmap, specified in the **Mask** member. Each bit in the mask corresponds to a byte in the pattern, and specifies whether the corresponding byte in the incoming packet should be matched against the corresponding byte in the pattern. If all the bytes compared by the network adapter match, the packet is a match and the network adapter should generate a wake-up event.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_WAKE_SOURCE_BITMAP_PARAMETERS_INIT**](../netwakesource/nf-netwakesource-net_wake_source_bitmap_parameters_init.md)

[**NetWakeSourceGetBitmapParameters**](../netwakesource/nf-netwakesource-netwakesourcegetbitmapparameters.md)

