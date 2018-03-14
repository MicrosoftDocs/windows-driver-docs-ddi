---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetMaximumPacketSize
title: VmbChannelInitSetMaximumPacketSize function
author: windows-driver-content
description: The VmbChannelInitSetMaximumPacketSize function sets the maximum packet size that can be delivered through a channel, which is the maximum size that will ever be specified by the VmbPacketSend function.
old-location: netvista\vmbchannelinitsetmaximumpacketsize.htm
old-project: netvista
ms.assetid: E1CD6911-A54F-4B24-B9BE-59EF9F2C30E5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: VmbChannelInitSetMaximumPacketSize, VmbChannelInitSetMaximumPacketSize function [Network Drivers Starting with Windows Vista], netvista.vmbchannelinitsetmaximumpacketsize, vmbuskernelmodeclientlibapi/VmbChannelInitSetMaximumPacketSize
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
-	VmbChannelInitSetMaximumPacketSize
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelInitSetMaximumPacketSize function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The  <b>VmbChannelInitSetMaximumPacketSize</b> function sets the maximum packet size that can be delivered through a channel, which is the maximum size that will ever be specified by the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a> function.  


## -syntax


````
NTSTATUS VmbChannelInitSetMaximumPacketSize(
  _In_ VMBCHANNEL         Channel,
  _In_ range_(>,0) UINT32 PacketSize
);
````


## -parameters




### -param Channel [in]

A handle for the channel.  


### -param PacketSize [in]

Maximum size, in bytes, of a packet.


## -returns



<b>VmbChannelInitSetMaximumPacketSize</b> returns one of the following status values: 

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
The <i>PacketSize</i> value is invalid. Zero (0) is invalid.

</td>
</tr>
</table>
 




## -remarks



This function can only be called during channel initialization. 

The size of
the ring buffers is, in part, based on this maximum packet size. 




## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a>



 

 


