---
UID: NF:vmbuskernelmodeclientlibapi.VmbServerChannelInitSetFlags
title: VmbServerChannelInitSetFlags function
author: windows-driver-content
description: The VmbServerChannelInitSetFlags function sets flags unique to server channel endpoints.
old-location: netvista\vmbserverchannelinitsetflags.htm
old-project: netvista
ms.assetid: F6DBD055-8B6F-4B2B-B584-3C06979DD6DF
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: VmbServerChannelInitSetFlags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbServerChannelInitSetFlags
req.alt-loc: VmbusKernelModeClientLibApi.h
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
req.typenames: *PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbServerChannelInitSetFlags function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbServerChannelInitSetFlags</b> function sets flags unique to server channel endpoints.



## -syntax

````
NTSTATUS VmbServerChannelInitSetFlags(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     Flags
);
````


## -parameters

### -param Channel [in]

A handle for a channel.  


### -param Flags [in]

A collection of bit flags to set.


## -returns
<b>VmbServerChannelInitSetFlags</b> returns the following status values: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>The <i>Flags</i> value has invalid bits set.

 


## -remarks
