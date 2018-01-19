---
UID: NS:wditypes._WDI_CHANNEL_MAPPING_ENTRY
title: _WDI_CHANNEL_MAPPING_ENTRY
author: windows-driver-content
description: The WDI_CHANNEL_MAPPING_ENTRY structure defines a channel mapping entry.
old-location: netvista\wdi_channel_mapping_entry.htm
old-project: netvista
ms.assetid: F05DAD5F-C0A4-46E0-8069-7CEF5B6C5707
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_CHANNEL_MAPPING_ENTRY, *PWDI_CHANNEL_MAPPING_ENTRY, WDI_CHANNEL_MAPPING_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_CHANNEL_MAPPING_ENTRY
req.alt-loc: wditypes.hpp
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PWDI_CHANNEL_MAPPING_ENTRY, WDI_CHANNEL_MAPPING_ENTRY
req.product: Windows 10 or later.
---

# _WDI_CHANNEL_MAPPING_ENTRY structure



## -description
The 
  WDI_CHANNEL_MAPPING_ENTRY structure defines a channel mapping entry.



## -syntax

````
typedef struct _WDI_CHANNEL_MAPPING_ENTRY {
  UINT32 ChannelNumber;
  UINT32 ChannelCenterFrequency;
} WDI_CHANNEL_MAPPING_ENTRY, *PWDI_CHANNEL_MAPPING_ENTRY;
````


## -struct-fields

### -field ChannelNumber

Specifies the logical channel number.


### -field ChannelCenterFrequency

Specifies the center frequency for the channel in MHz.


## -remarks
