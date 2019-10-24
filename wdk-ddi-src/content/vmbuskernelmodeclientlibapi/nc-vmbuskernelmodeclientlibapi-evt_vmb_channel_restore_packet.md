---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_RESTORE_PACKET
title: EVT_VMB_CHANNEL_RESTORE_PACKET (vmbuskernelmodeclientlibapi.h)
description: The EvtVmbChannelRestorePacket callback function is invoked when the virtualization service provider (VSP) server endpoint must restore the state associated with a packet object.
old-location: netvista\evt_vmb_channel_restore_packet.htm
tech.root: netvista
ms.assetid: 9C89CFCB-4B8A-40D3-B982-2F7836A636A3
ms.date: 05/02/2018
ms.keywords: EVT_VMB_CHANNEL_RESTORE_PACKET, EVT_VMB_CHANNEL_RESTORE_PACKET callback, EvtVmbChannelRestorePacket, EvtVmbChannelRestorePacket callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_RESTORE_PACKET, PFN_VMB_CHANNEL_RESTORE_PACKET callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_restore_packet, vmbuskernelmodeclientlibapi/EvtVmbChannelRestorePacket
ms.topic: callback
f1_keywords:
 - "vmbuskernelmodeclientlibapi/PFN_VMB_CHANNEL_RESTORE_PACKET"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- VmbusKernelModeClientLibApi.h
api_name:
- PFN_VMB_CHANNEL_RESTORE_PACKET
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_VMB_CHANNEL_RESTORE_PACKET callback function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelRestorePacket</i> callback function is invoked when the virtualization service provider (VSP) server
endpoint must restore the state associated with a packet object.  


## -parameters




### -param Channel [in]

The channel on which the packet arrives.


### -param LibBuf [in]

Pointer to packet object state internal to the Kernel Mode Client Library (KMCL).



### -param LibBufSize [in]

Size of the <i>LibBuf</i> parameter, in bytes.



### -param SaveBuf [in]

Pointer to transaction state specific to the VSP.



### -param SaveBufSize [in]

Size of the <i>SaveBuf</i> parameter, in bytes.



## -returns



<i>EvtVmbChannelRestorePacket</i> returns a status code.




## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetsaverestorepacketcallbacks">VmbServerChannelInitSetSaveRestorePacketCallbacks</a> function sets a callback function for restoring packets for each channel.

In order
to restore an in-flight packet object, the VSP must allocate a new packet
by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketallocate">VmbPacketAllocate</a> function. The VSP restores the packet to the previous state by passing <i>LibBuf</i> and <i>LibBufSize</i> to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketrestore">VmbPacketRestore</a> function.
If the VSP provided any internal state for the transaction in the <i>EvtVmbChannelSavePacket</i>
callback function, then this is provided in <i>SaveBuf</i>, and restored by the VSP.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_restore_packet">EvtVmbChannelSavePacket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketallocate">VmbPacketAllocate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketrestore">VmbPacketRestore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetsaverestorepacketcallbacks">VmbServerChannelInitSetSaveRestorePacketCallbacks</a>
 

 

