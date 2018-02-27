---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetFlags
title: VmbChannelInitSetFlags function
author: windows-driver-content
description: The VmbChannelInitSetFlags function sets flags common to server or client channel endpoints.
old-location: netvista\vmbchannelinitsetflags.htm
old-project: netvista
ms.assetid: 12525F3C-12D6-477E-8C7D-3DE9AAA044AE
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: VmbChannelInitSetFlags, VmbChannelInitSetFlags function [Network Drivers Starting with Windows Vista], netvista.vmbchannelinitsetflags, vmbuskernelmodeclientlibapi/VmbChannelInitSetFlags
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbChannelInitSetFlags
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelInitSetFlags function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetFlags</b> function sets flags common to server or client channel endpoints.


## -syntax


````
NTSTATUS VmbChannelInitSetFlags(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     Flags
);
````


## -parameters




### -param Channel [in]

A handle for the channel.



### -param Flags [in]

A collection of bit flags to set.


## -returns



<b>VmbChannelInitSetFlags</b> can return one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>Flags</i> has invalid bits.

</td>
</tr>
</table>
 



