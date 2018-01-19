---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_POST_STARTED
title: EVT_VMB_CHANNEL_POST_STARTED
author: windows-driver-content
description: The EvtVmbChannelPostStarted callback function is invoked at either endpoint after packets can be received from the opposite endpoint.
old-location: netvista\evt_vmb_channel_post_started.htm
old-project: netvista
ms.assetid: 0F48459F-BA02-4A0E-9228-BC064A6AD150
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES
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
req.alt-api: PFN_VMB_CHANNEL_POST_STARTED
req.alt-loc: VmbusKernelModeClientLibApi.h
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
req.typenames: *PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_POST_STARTED callback



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelPostStarted</i> callback function is invoked at either endpoint after packets can be received from
the opposite endpoint.  



## -prototype

````
EVT_VMB_CHANNEL_POST_STARTED EvtVmbChannelPostStarted;

VOID EvtVmbChannelPostStarted(
  _In_ VMBCHANNEL Channel
)
{ ... }

typedef EVT_VMB_CHANNEL_POST_STARTED PFN_VMB_CHANNEL_POST_STARTED;
````


## -parameters

### -param Channel [in]

The channel for these endpoints.


## -returns
This callback function does not return a value.


## -remarks
After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelPostStarted</i>, by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

After a channel has been  
configured, the Kernel Mode Client Library (KMCL) client calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a> function to open the channel.  When a channel is opened, KMCL invokes the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md">EvtVmbChannelOpened</a> callback function. After the channel endpoints can receive packets but before packets are processed, KMCL invokes the <i>EvtVmbChannelPostStarted</i> callback.

You can wait for sent packets to complete in this function, such as by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a> function.


## -see-also
<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md">EvtVmbChannelOpened</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_post_started.md">EvtVmbChannelPostStarted</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_POST_STARTED callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

