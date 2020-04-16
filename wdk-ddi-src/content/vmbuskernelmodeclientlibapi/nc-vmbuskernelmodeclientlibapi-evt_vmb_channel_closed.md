---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_CLOSED
title: EVT_VMB_CHANNEL_CLOSED (vmbuskernelmodeclientlibapi.h)
description: The EvtVmbChannelClosed callback function is invoked when the client endpoint in the guest virtual machine closes a channel by using the VmbChannelDisable function, or the opposite endpoint rescinds or closes the channel.
old-location: netvista\evt_vmb_channel_closed.htm
tech.root: netvista
ms.assetid: 457FADB8-4126-43A8-AA38-E3D722728459
ms.date: 05/02/2018
keywords: ["EVT_VMB_CHANNEL_CLOSED callback function"]
ms.keywords: EVT_VMB_CHANNEL_CLOSED, EVT_VMB_CHANNEL_CLOSED callback, EvtVmbChannelClosed, EvtVmbChannelClosed callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_CLOSED, PFN_VMB_CHANNEL_CLOSED callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_closed, vmbuskernelmodeclientlibapi/EvtVmbChannelClosed
f1_keywords:
 - "vmbuskernelmodeclientlibapi/PFN_VMB_CHANNEL_CLOSED"
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
- PFN_VMB_CHANNEL_CLOSED
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_VMB_CHANNEL_CLOSED callback function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelClosed</i> callback function is invoked when the client endpoint in the guest virtual machine closes a
channel by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchanneldisable">VmbChannelDisable</a> function, or the opposite endpoint rescinds or closes the 
channel.  


## -parameters




### -param Channel [in]

The channel that the guest virtual machine closes.


## -remarks



After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelClosed</i>, by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

After this callback function finishes on the host, the channel 
is either closed or disabled, depending on whether the guest closed 
the channel or the Kernel Mode Client Library (KMCL) client called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchanneldisable">VmbChannelDisable</a>, 
respectively.  

On the guest, the channel always becomes disabled. It 
must be restarted by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelenable">VmbChannelEnable</a> function.  

After this  is function invoked, packets can be queued, but they cannot be sent.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchanneldisable">VmbChannelDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelenable">VmbChannelEnable</a>
 

 

