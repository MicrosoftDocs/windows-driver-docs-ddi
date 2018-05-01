---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelPacketDeferToPassive
title: VmbChannelPacketDeferToPassive function
author: windows-driver-content
description: The VmbChannelPacketDeferToPassive function is called by the client driver to defer a packet passed to it by the EvtVmbChannelProcessPacket callback function.
old-location: netvista\vmbchannelpacketdefertopassive.htm
old-project: netvista
ms.assetid: 796F849F-7281-4AE9-BE0D-350D24A39C61
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbChannelPacketDeferToPassive, VmbChannelPacketDeferToPassive function [Network Drivers Starting with Windows Vista], netvista.vmbchannelpacketdefertopassive, vmbuskernelmodeclientlibapi/VmbChannelPacketDeferToPassive
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
-	VmbChannelPacketDeferToPassive
product: Windows
targetos: Windows
req.typenames: 
---

# VmbChannelPacketDeferToPassive function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketDeferToPassive</b> function is called by the client driver to defer a packet
passed to it by the <a href="https://msdn.microsoft.com/46020122-0B0E-4C05-8B13-68100B227E93">EvtVmbChannelProcessPacket</a> callback function.  


## -parameters




### -param PacketCompletionContext [in]

A  handle that identifies the incoming packet and is used to refer to the packet
once processing is finished.  


## -returns



This function does not return a value.




## -remarks



A deferred packet goes back onto the parsing queue. It is guaranteed to be
parsed again at PASSIVE_LEVEL.


This routine is designed to only be called in-line from <a href="https://msdn.microsoft.com/46020122-0B0E-4C05-8B13-68100B227E93">EvtVmbChannelProcessPacket</a>.




## -see-also




<a href="https://msdn.microsoft.com/46020122-0B0E-4C05-8B13-68100B227E93">EvtVmbChannelProcessPacket</a>
 

 

