---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_PROCESSING_COMPLETE
title: EVT_VMB_CHANNEL_PROCESSING_COMPLETE
author: windows-driver-content
description: The EvtVmbChannelProcessingComplete callback function is invoked when a group of packets has been delivered by the EvtVmbChannelProcessPacket function, if there is a pause before delivering subsequent packets.
old-location: netvista\evt_vmb_channel_processing_complete.htm
old-project: netvista
ms.assetid: E30A169E-0EC6-4128-B268-5FC1CD37A877
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.evt_vmb_channel_processing_complete, EvtVmbChannelProcessingComplete callback function [Network Drivers Starting with Windows Vista], EvtVmbChannelProcessingComplete, EVT_VMB_CHANNEL_PROCESSING_COMPLETE, EVT_VMB_CHANNEL_PROCESSING_COMPLETE, vmbuskernelmodeclientlibapi/EvtVmbChannelProcessingComplete, PFN_VMB_CHANNEL_PROCESSING_COMPLETE callback function pointer [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_PROCESSING_COMPLETE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	VmbusKernelModeClientLibApi.h
apiname:
-	PFN_VMB_CHANNEL_PROCESSING_COMPLETE
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_PROCESSING_COMPLETE callback


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelProcessingComplete</i> callback function is invoked when a group of packets has been delivered by
the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet.md">EvtVmbChannelProcessPacket</a> function, if there is a pause before delivering subsequent packets.   


## -prototype


````
EVT_VMB_CHANNEL_PROCESSING_COMPLETE EvtVmbChannelProcessingComplete;

VOID EvtVmbChannelProcessingComplete(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     PacketsProcessed
)
{ ... }

typedef EVT_VMB_CHANNEL_PROCESSING_COMPLETE PFN_VMB_CHANNEL_PROCESSING_COMPLETE;
````


## -parameters




#### - Channel [in]

The channel one which the packets are delivered.


#### - PacketsProcessed [in]

The number of packets which were delivered in this batch.


## -returns


This callback function does not return a value.



## -remarks


The client driver registers its implementation of this callback function by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks.md">VmbChannelInitSetProcessPacketCallbacks</a> function. 

A pause in packet processing might occur because the
incoming ring buffer was empty.

This callback function can be invoked at DISPATCH_LEVEL or lower, unless the channel
has been configured to defer packet processing to a worker thread.



## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks.md">VmbChannelInitSetProcessPacketCallbacks</a>

<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet.md">EvtVmbChannelProcessPacket</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_PROCESSING_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

