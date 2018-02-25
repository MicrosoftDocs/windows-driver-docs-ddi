---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_OPENED
title: EVT_VMB_CHANNEL_OPENED
author: windows-driver-content
description: The EvtVmbChannelOpened callback function is invoked when the client endpoint in the guest virtual machine opens a channel which has been offered to it.
old-location: netvista\evt_vmb_channel_opened.htm
old-project: netvista
ms.assetid: 4E35AAA4-B9BA-4248-BBE6-FB576CAFD046
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: EVT_VMB_CHANNEL_OPENED, EvtVmbChannelOpened, EvtVmbChannelOpened callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_OPENED, PFN_VMB_CHANNEL_OPENED callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_opened, vmbuskernelmodeclientlibapi/EvtVmbChannelOpened
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	VmbusKernelModeClientLibApi.h
apiname:
-	PFN_VMB_CHANNEL_OPENED
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_OPENED callback


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelOpened</i> callback function is invoked when the client endpoint in the guest virtual machine opens a
channel which has been offered to it. 


## -prototype


````
EVT_VMB_CHANNEL_OPENED EvtVmbChannelOpened;

NTSTATUS
 EvtVmbChannelOpened(
  _In_ VMBCHANNEL Channel
)
{ ... }

typedef EVT_VMB_CHANNEL_OPENED PFN_VMB_CHANNEL_OPENED;
````


## -parameters




### -param Channel [in]

The channel that the guest virtual machine opens.


## -returns



EvtVmbChannelClosed returns a status code.




## -remarks



After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelOpened</i>, by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

After a channel has been  
configured, the Kernel Mode Client Library (KMCL) client calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a> function.  On the host, this 
function offers a channel to the guest.  On the guest, this function 
accepts an existing offer or waits for such an offer to arrive.  When a channel is opened, KMCL invokes the <i>EvtVmbChannelOpened</i> callback function.  
After this callback finishes, the channel
is in the open state.

  Before this callback function is invoked, packets can
be queued, but they cannot be sent.


If the client driver returns a failure  status code, the channel
rolls back to a state where no traffic flows.




## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_OPENED callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

