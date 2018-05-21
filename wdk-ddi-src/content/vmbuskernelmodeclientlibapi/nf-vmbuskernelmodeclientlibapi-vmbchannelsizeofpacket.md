---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSizeofPacket
title: VmbChannelSizeofPacket function
author: windows-driver-content
description: The VmbChannelSizeofPacket function calculates the necessary size for buffers to be used with the VmbPacketInitialize function.
old-location: netvista\vmbchannelsizeofpacket.htm
old-project: netvista
ms.assetid: 3E7EE060-4B1F-4B28-A617-5B1393CEE936
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbChannelSizeofPacket, VmbChannelSizeofPacket function [Network Drivers Starting with Windows Vista], netvista.vmbchannelsizeofpacket, vmbuskernelmodeclientlibapi/VmbChannelSizeofPacket
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
-	VmbChannelSizeofPacket
product:
- Windows
targetos: Windows
req.typenames: 
---

# VmbChannelSizeofPacket function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSizeofPacket</b> function calculates the necessary size for buffers to be used with
the <a href="https://msdn.microsoft.com/D5D8D994-0BB6-44FC-A696-F2E0264445C1">VmbPacketInitialize</a> function.


## -parameters




### -param Channel [in]

A handle for a channel.  


## -returns



The necessary buffer size, in bytes.




## -see-also




<a href="https://msdn.microsoft.com/D5D8D994-0BB6-44FC-A696-F2E0264445C1">VmbPacketInitialize</a>
 

 

