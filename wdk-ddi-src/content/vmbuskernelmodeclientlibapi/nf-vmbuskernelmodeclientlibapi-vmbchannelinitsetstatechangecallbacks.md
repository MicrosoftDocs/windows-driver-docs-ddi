---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetStateChangeCallbacks
title: VmbChannelInitSetStateChangeCallbacks function
author: windows-driver-content
description: The VmbChannelInitSetStateChangeCallbacks function sets optional callback functions for state changes.
old-location: netvista\vmbchannelinitsetstatechangecallbacks.htm
old-project: netvista
ms.assetid: 4E6088EA-7081-4B80-8F83-15B39A0F30AB
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: VmbChannelInitSetStateChangeCallbacks, VmbChannelInitSetStateChangeCallbacks function [Network Drivers Starting with Windows Vista], netvista.vmbchannelinitsetstatechangecallbacks, vmbuskernelmodeclientlibapi/VmbChannelInitSetStateChangeCallbacks
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
-	VmbChannelInitSetStateChangeCallbacks
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelInitSetStateChangeCallbacks function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetStateChangeCallbacks</b>  function sets optional callback functions for state changes.


## -syntax


````
NTSTATUS VmbChannelInitSetStateChangeCallbacks(
  _In_ VMBCHANNEL                          Channel,
  _In_ PVMB_CHANNEL_STATE_CHANGE_CALLBACKS StateChangeCallbacks
);
````


## -parameters




### -param Channel [in]

A handle for a channel.  


### -param StateChangeCallbacks [in]

A structure of state change callbacks to set.


## -returns



<b>VmbChannelInitSetStateChangeCallbacks</b> returns one of the following status values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function finished successfully.

</td>
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
The <i>StateChangeCallbacks</i> value is the wrong version or size. 

</td>
</tr>
</table>
 



