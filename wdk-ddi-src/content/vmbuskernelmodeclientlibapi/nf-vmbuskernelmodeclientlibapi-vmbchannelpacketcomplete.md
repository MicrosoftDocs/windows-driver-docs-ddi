---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelPacketComplete
title: VmbChannelPacketComplete function
author: windows-driver-content
description: The VmbChannelPacketComplete function cleans up any outstanding memory mappings, releases any buffers in use, and, if the opposite endpoint requested a completion packet, sends a completion packet.
old-location: netvista\vmbchannelpacketcomplete.htm
old-project: netvista
ms.assetid: 1DC215DF-1F53-4910-84D5-17E13BE6202A
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbChannelPacketComplete, VmbChannelPacketComplete function [Network Drivers Starting with Windows Vista], netvista.vmbchannelpacketcomplete, vmbuskernelmodeclientlibapi/VmbChannelPacketComplete
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
-	VmbChannelPacketComplete
product: Windows
targetos: Windows
req.typenames: 
---

# VmbChannelPacketComplete function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketComplete</b>  function cleans up any
outstanding memory mappings, releases any buffers in use, and, if the opposite endpoint requested a completion packet, sends a
completion packet. 


## -parameters




### -param PacketCompletionContext [in]

A  handle that identifies the incoming packet and is used to refer to the packet
once processing is finished.  


### -param PacketCompletionBuffer [in]

A buffer of completion data to be sent back to the originating endpoint.  Although this usually contains just a status value, the contents are up to the client driver.



### -param BufSize [in]

The size, in bytes, of the completion buffer.


## -returns



This function does not return a value.




## -remarks



This function is called when the client driver is finished
processing a packet.  This function may be called directly from the packet parsing function
or it may be called later.  



