---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_SUSPEND
title: EVT_VMB_CHANNEL_SUSPEND (vmbuskernelmodeclientlibapi.h)
description: The EvtVmbChannelSuspend callback function is invoked at the server endpoint when the channel is being closed or deleted by the client endpoint, which moves the server into the Stopped state.
old-location: netvista\evt_vmb_channel_suspend.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["EVT_VMB_CHANNEL_SUSPEND callback function"]
ms.keywords: EVT_VMB_CHANNEL_SUSPEND, EVT_VMB_CHANNEL_SUSPEND callback, EvtVmbChannelSuspend, EvtVmbChannelSuspend callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_SUSPEND, PFN_VMB_CHANNEL_SUSPEND callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_suspend, vmbuskernelmodeclientlibapi/EvtVmbChannelSuspend
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_VMB_CHANNEL_SUSPEND
 - vmbuskernelmodeclientlibapi/EVT_VMB_CHANNEL_SUSPEND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - VmbusKernelModeClientLibApi.h
api_name:
 - EVT_VMB_CHANNEL_SUSPEND
---

# EVT_VMB_CHANNEL_SUSPEND callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelSuspend</i> callback function is invoked at the server endpoint when the channel is being
closed or deleted by the client endpoint, which moves the server into the Stopped
state.

## -parameters

### -param Channel 

[in]
The channel which is suspended.

## -remarks

After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelSuspend</i>, by using the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

If a running channel is suspended by using the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpause">VmbChannelPause</a> function or closed by using the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchanneldisable">VmbChannelDisable</a> function or by the opposite endpoint, Kernel Mode Client Library (KMCL) calls <i>EvtVmbChannelSuspend</i>.  This callback guarantees that no more 
<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet">EvtVmbChannelProcessPacket</a> callbacks are running or will be queued.

<i>EvtVmbChannelSuspend</i> is also a 
notification that the KMCL client must eventually complete all outstanding 
packets indicated by using  <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet">EvtVmbChannelProcessPacket</a> These packets do 
not have to be completed synchronously.  KMCL blocks until they have 
been completed.  

The KMCL client must also stop sending packets by using the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsend">VmbPacketSend</a>, <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl">VmbPacketSendWithExternalMdl</a>, or <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns">VmbPacketSendWithExternalPfns</a> functions.  



A call to <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpause">VmbChannelPause</a> on an active channel blocks until 
<i>EvtVmbChannelSuspend</i> is called and no more outstanding incoming packets exist.  
A call to <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchanneldisable">VmbChannelDisable</a> block until the channel is paused and closed.

This function does guarantee completion of outstanding transactions.  The client may be buggy, malicious,
or the guest virtual machine may have crashed.  The server must retire any outstanding transactions, probably by cancelling them.

## -see-also

<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet">EvtVmbChannelProcessPacket</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchanneldisable">VmbChannelDisable</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpause">VmbChannelPause</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsend">VmbPacketSend</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl">VmbPacketSendWithExternalMdl</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns">VmbPacketSendWithExternalPfns</a>

