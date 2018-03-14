---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_PROCESS_PACKET
title: EVT_VMB_CHANNEL_PROCESS_PACKET
author: windows-driver-content
description: The EvtVmbChannelProcessPacket callback function is invoked when a packet arrives in the incoming ring buffer.
old-location: netvista\evt_vmb_channel_process_packet.htm
old-project: netvista
ms.assetid: 46020122-0B0E-4C05-8B13-68100B227E93
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EVT_VMB_CHANNEL_PROCESS_PACKET, EvtVmbChannelProcessPacket, EvtVmbChannelProcessPacket callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_PROCESS_PACKET, PFN_VMB_CHANNEL_PROCESS_PACKET callback function pointer [Network Drivers Starting with Windows Vista], VMBUS_CHANNEL_PROCESS_PACKET_FLAGS, netvista.evt_vmb_channel_process_packet, vmbuskernelmodeclientlibapi/EvtVmbChannelProcessPacket
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	PFN_VMB_CHANNEL_PROCESS_PACKET
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_PROCESS_PACKET callback


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelProcessPacket</i> callback function is invoked when a packet arrives in the incoming ring buffer.



## -prototype


````
EVT_VMB_CHANNEL_PROCESS_PACKET EvtVmbChannelProcessPacket;

VOID EvtVmbChannelProcessPacket(
  _In_ VMBCHANNEL                       Channel,
  _In_ VMBPACKETCOMPLETION              Packet,
  _In_ reads_bytes_(BufferLength) PVOID Buffer,
  _In_ UINT32                           BufferLength,
  _In_ UINT32                           Flags
)
{ ... }

typedef EVT_VMB_CHANNEL_PROCESS_PACKET PFN_VMB_CHANNEL_PROCESS_PACKET;
````


## -parameters




### -param Channel [in]

The channel on which the packet arrives.


### -param Packet [in]

The completion context, which identifies this packet to Kernel Mode Client Library (KMCL) when the transaction can be retired.



### -param Buffer [in]

The packet which was sent by the opposite endpoint.  This value does not contain the VMBus and KMCL headers.



### -param BufferLength [in]

The length of the <i>Buffer</i> parameter, in bytes.


### -param Flags [in]

Flags. Possible values include the following: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_PROCESS_PACKET_FLAGS"></a><a id="vmbus_channel_process_packet_flags"></a><dl>
<dt><b>VMBUS_CHANNEL_PROCESS_PACKET_FLAGS</b></dt>
<dt>0x1</dt>
</dl>
</td>
<td width="60%">
The packet references
external data. This data can be retrieved by using
the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketgetexternaldata.md">VmbChannelPacketGetExternalData</a> function.

</td>
</tr>
</table>
 


## -returns



This callback function does not return a value.




## -remarks



The client driver registers its implementation of this callback function by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks.md">VmbChannelInitSetProcessPacketCallbacks</a> function. 

Every time you invoke this function, you must eventually call
the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete.md">VmbChannelPacketComplete</a> function.

This callback function can be invoked at DISPATCH_LEVEL or lower, unless the channel
has been configured to defer packet processing to a worker thread.




## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete.md">VmbChannelPacketComplete</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketgetexternaldata.md">VmbChannelPacketGetExternalData</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks.md">VmbChannelInitSetProcessPacketCallbacks</a>



 

 


