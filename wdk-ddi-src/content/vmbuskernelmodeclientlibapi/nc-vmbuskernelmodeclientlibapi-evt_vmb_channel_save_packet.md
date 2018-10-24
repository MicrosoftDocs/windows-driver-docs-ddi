---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_SAVE_PACKET
title: EVT_VMB_CHANNEL_SAVE_PACKET
author: windows-driver-content
description: The EvtVmbChannelSavePacket callback function is invoked when the virtualization service provider (VSP) endpoint must save the state associated with a packet.
old-location: netvista\evt_vmb_channel_save_packet.htm
tech.root: netvista
ms.assetid: 92CC3C36-D10C-4C6B-8BB4-476E72AD684C
ms.date: 05/02/2018
ms.keywords: EVT_VMB_CHANNEL_SAVE_PACKET, EVT_VMB_CHANNEL_SAVE_PACKET callback, EvtVmbChannelSavePacket, EvtVmbChannelSavePacket callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_SAVE_PACKET, PFN_VMB_CHANNEL_SAVE_PACKET callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_save_packet, vmbuskernelmodeclientlibapi/EvtVmbChannelSavePacket
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	PFN_VMB_CHANNEL_SAVE_PACKET
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_VMB_CHANNEL_SAVE_PACKET callback function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelSavePacket</i> callback function is invoked when the virtualization service provider (VSP) endpoint must save the state associated with a packet.  


## -parameters




### -param Channel [in]

The channel on which the packet arrives.


### -param Packet [in]

The packet for which VSP saves state.


### -param SaveBuf [out]

The buffer into which to save the state.



### -param SaveBufSize [in]

Size of the <i>SaveBuf</i> parameter, in bytes.




### -param BytesNeeded [out]

Size necessary to save the state of the transaction, in bytes.



## -returns



<i>EvtVmbChannelSavePacket</i> returns a status code.




## -remarks



The <a href="https://msdn.microsoft.com/2E704BF1-21E2-498E-82C2-2B55BF44D044">VmbServerChannelInitSetSaveRestorePacketCallbacks</a> function sets a callback function for saving packets for each channel.

The VSP saves the state associated with the transaction that is unique to the VSP.  The Kernel Mode Client Library (KMCL)
saves its own state.

This function is invoked for each packet object that is currently in use.  The first invocation passes a zero (0) value for the <i>SaveBufSize</i> parameter.  This call fails if there is any state that needs to be saved, which fills the <i>BytesNeeded</i> with the actual size requirement.  If this first invocation
returns a failure code, the KMCL calls a second time with a buffer of at least
the length stipulated in the first call.




## -see-also




<a href="https://msdn.microsoft.com/2E704BF1-21E2-498E-82C2-2B55BF44D044">VmbServerChannelInitSetSaveRestorePacketCallbacks</a>
 

 

