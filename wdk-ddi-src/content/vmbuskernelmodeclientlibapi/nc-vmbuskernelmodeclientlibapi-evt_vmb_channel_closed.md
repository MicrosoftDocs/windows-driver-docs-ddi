---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_CLOSED
title: EVT_VMB_CHANNEL_CLOSED
author: windows-driver-content
description: The EvtVmbChannelClosed callback function is invoked when the client endpoint in the guest virtual machine closes a channel by using the VmbChannelDisable function, or the opposite endpoint rescinds or closes the channel.
old-location: netvista\evt_vmb_channel_closed.htm
old-project: netvista
ms.assetid: 457FADB8-4126-43A8-AA38-E3D722728459
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.evt_vmb_channel_closed, EvtVmbChannelClosed callback function [Network Drivers Starting with Windows Vista], EvtVmbChannelClosed, EVT_VMB_CHANNEL_CLOSED, EVT_VMB_CHANNEL_CLOSED, vmbuskernelmodeclientlibapi/EvtVmbChannelClosed, PFN_VMB_CHANNEL_CLOSED callback function pointer [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_CLOSED
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
-	PFN_VMB_CHANNEL_CLOSED
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_CLOSED callback


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelClosed</i> callback function is invoked when the client endpoint in the guest virtual machine closes a
channel by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchanneldisable.md">VmbChannelDisable</a> function, or the opposite endpoint rescinds or closes the 
channel.  


## -prototype


````
EVT_VMB_CHANNEL_CLOSED EvtVmbChannelClosed;

VOID EvtVmbChannelClosed(
  _In_ VMBCHANNEL Channel
)
{ ... }

typedef EVT_VMB_CHANNEL_CLOSED PFN_VMB_CHANNEL_CLOSED;
````


## -parameters




### -param Channel [in]

The channel that the guest virtual machine closes.


## -returns


This callback function does not return a value.



## -remarks


After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelClosed</i>, by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

After this callback function finishes on the host, the channel 
is either closed or disabled, depending on whether the guest closed 
the channel or the Kernel Mode Client Library (KMCL) client called <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchanneldisable.md">VmbChannelDisable</a>, 
respectively.  

On the guest, the channel always becomes disabled. It 
must be restarted by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a> function.  

After this  is function invoked, packets can be queued, but they cannot be sent.



## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchanneldisable.md">VmbChannelDisable</a>

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_CLOSED callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

