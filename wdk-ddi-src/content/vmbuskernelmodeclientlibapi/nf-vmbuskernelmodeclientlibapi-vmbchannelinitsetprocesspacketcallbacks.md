---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetProcessPacketCallbacks
title: VmbChannelInitSetProcessPacketCallbacks function
author: windows-driver-content
description: The VmbChannelInitSetProcessPacketCallbacks function sets callback functions for packet processing.
old-location: netvista\vmbchannelinitsetprocesspacketcallbacks.htm
old-project: netvista
ms.assetid: 437DC9C5-CE73-45E8-AC4A-CFF9249809AD
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: VmbChannelInitSetProcessPacketCallbacks
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
req.alt-api: VmbChannelInitSetProcessPacketCallbacks
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
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
req.typenames: *PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelInitSetProcessPacketCallbacks function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetProcessPacketCallbacks</b>  function sets callback functions for packet processing. 



## -syntax

````
 VmbChannelInitSetProcessPacketCallbacks(
  _In_     VMBCHANNEL                          Channel,
  _In_     PFN_VMB_CHANNEL_PROCESS_PACKET      ProcessPacketCallback,
  _In_opt_ PFN_VMB_CHANNEL_PROCESSING_COMPLETE ProcessingCompleteCallback

);
````


## -parameters

### -param Channel [in]

A handle for the channel.  


### -param ProcessPacketCallback [in]

A callback function to call when a packet is     ready for processing.


### -param ProcessingCompleteCallback
</i> [in, optional]
<dd>

A callback function to call     when processing of a batch of packets has been completed.


## -returns
 returns one of the following status values: 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function finished successfully.
<dl>
<dt><b> STATUS_INVALID_PARAMETER_1</b></dt>
</dl>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

 


## -remarks
This function is only meaningful if Kernel Mode Client Library (KMCL) queue
management is not suppressed.  

<b>ProcessPacketCallback</b> is invoked for every packet that
is received.  <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_processing_complete.md">EvtVmbChannelProcessingComplete</a> will be invoked every time the ring buffer that contains incoming packets transitions from non-empty to empty. This happens
after the last invocation of <b>ProcessPacketCallback</b> in a single batch.


## -see-also
<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_processing_complete.md">EvtVmbChannelProcessingComplete</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks.md">ProcessPacketCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelInitSetProcessPacketCallbacks function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

