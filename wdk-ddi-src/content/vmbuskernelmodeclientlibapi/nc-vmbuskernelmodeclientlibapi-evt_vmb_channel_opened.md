---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_OPENED
title: EVT_VMB_CHANNEL_OPENED (vmbuskernelmodeclientlibapi.h)
description: The EvtVmbChannelOpened callback function is invoked when the client endpoint in the guest virtual machine opens a channel which has been offered to it.
old-location: netvista\evt_vmb_channel_opened.htm
tech.root: netvista
ms.assetid: 4E35AAA4-B9BA-4248-BBE6-FB576CAFD046
ms.date: 05/02/2018
keywords: ["EVT_VMB_CHANNEL_OPENED callback function"]
ms.keywords: EVT_VMB_CHANNEL_OPENED, EVT_VMB_CHANNEL_OPENED callback, EvtVmbChannelOpened, EvtVmbChannelOpened callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_OPENED, PFN_VMB_CHANNEL_OPENED callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_opened, vmbuskernelmodeclientlibapi/EvtVmbChannelOpened
f1_keywords:
 - "vmbuskernelmodeclientlibapi/PFN_VMB_CHANNEL_OPENED"
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
- PFN_VMB_CHANNEL_OPENED
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_VMB_CHANNEL_OPENED callback function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelOpened</i> callback function is invoked when the client endpoint in the guest virtual machine opens a
channel which has been offered to it. 


## -parameters




### -param Channel [in]

The channel that the guest virtual machine opens.


## -returns



EvtVmbChannelClosed returns a status code.




## -remarks



After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelOpened</i>, by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

After a channel has been  
configured, the Kernel Mode Client Library (KMCL) client calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelenable">VmbChannelEnable</a> function.  On the host, this 
function offers a channel to the guest.  On the guest, this function 
accepts an existing offer or waits for such an offer to arrive.  When a channel is opened, KMCL invokes the <i>EvtVmbChannelOpened</i> callback function.  
After this callback finishes, the channel
is in the open state.

  Before this callback function is invoked, packets can
be queued, but they cannot be sent.


If the client driver returns a failure  status code, the channel
rolls back to a state where no traffic flows.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelenable">VmbChannelEnable</a>
 

 

