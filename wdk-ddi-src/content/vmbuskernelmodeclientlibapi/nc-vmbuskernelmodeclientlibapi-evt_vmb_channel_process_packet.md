---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_PROCESS_PACKET
title: EVT_VMB_CHANNEL_PROCESS_PACKET (vmbuskernelmodeclientlibapi.h)
description: The EvtVmbChannelProcessPacket callback function is invoked when a packet arrives in the incoming ring buffer.
old-location: netvista\evt_vmb_channel_process_packet.htm
tech.root: netvista
ms.assetid: 46020122-0B0E-4C05-8B13-68100B227E93
ms.date: 05/02/2018
keywords: ["EVT_VMB_CHANNEL_PROCESS_PACKET callback function"]
ms.keywords: EVT_VMB_CHANNEL_PROCESS_PACKET, EVT_VMB_CHANNEL_PROCESS_PACKET callback, EvtVmbChannelProcessPacket, EvtVmbChannelProcessPacket callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_PROCESS_PACKET, PFN_VMB_CHANNEL_PROCESS_PACKET callback function pointer [Network Drivers Starting with Windows Vista], VMBUS_CHANNEL_PROCESS_PACKET_FLAGS, netvista.evt_vmb_channel_process_packet, vmbuskernelmodeclientlibapi/EvtVmbChannelProcessPacket
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_VMB_CHANNEL_PROCESS_PACKET
 - vmbuskernelmodeclientlibapi/EVT_VMB_CHANNEL_PROCESS_PACKET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - VmbusKernelModeClientLibApi.h
api_name:
 - PFN_VMB_CHANNEL_PROCESS_PACKET
---

# EVT_VMB_CHANNEL_PROCESS_PACKET callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelProcessPacket</i> callback function is invoked when a packet arrives in the incoming ring buffer.

## -parameters

### -param Channel 

[in]
The channel on which the packet arrives.

### -param Packet 

[in]
The completion context, which identifies this packet to Kernel Mode Client Library (KMCL) when the transaction can be retired.

### -param Buffer 

[in]
The packet which was sent by the opposite endpoint.  This value does not contain the VMBus and KMCL headers.

### -param BufferLength 

[in]
The length of the <i>Buffer</i> parameter, in bytes.

### -param Flags 

[in]
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
the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpacketgetexternaldata">VmbChannelPacketGetExternalData</a> function.

</td>
</tr>
</table>

## -remarks

The client driver registers its implementation of this callback function by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks">VmbChannelInitSetProcessPacketCallbacks</a> function. 

Every time you invoke this function, you must eventually call
the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete">VmbChannelPacketComplete</a> function.

This callback function can be invoked at DISPATCH_LEVEL or lower, unless the channel
has been configured to defer packet processing to a worker thread.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks">VmbChannelInitSetProcessPacketCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete">VmbChannelPacketComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpacketgetexternaldata">VmbChannelPacketGetExternalData</a>

