---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_STARTED
title: EVT_VMB_CHANNEL_STARTED
author: windows-driver-content
description: The EvtVmbChannelStarted callback function is invoked at either endpoint when a channel is fully configured but before any packets have been delivered. This occurs when the opposite endpoint opened the channel or reopened it after closing it.
old-location: netvista\evt_vmb_channel_started.htm
tech.root: netvista
ms.assetid: C4F35016-3F93-4258-A42F-D692AF690020
ms.date: 5/2/2018
ms.keywords: EVT_VMB_CHANNEL_STARTED, EVT_VMB_CHANNEL_STARTED callback, EvtVmbChannelStarted, EvtVmbChannelStarted callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_STARTED, PFN_VMB_CHANNEL_STARTED callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_started, vmbuskernelmodeclientlibapi/EvtVmbChannelStarted
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
-	PFN_VMB_CHANNEL_STARTED
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_VMB_CHANNEL_STARTED callback function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelStarted</i> callback function is invoked at either endpoint when a channel is
fully configured but before any packets have been delivered.  This occurs when the opposite endpoint opened the channel or reopened it after closing it.  


## -parameters




### -param Channel [in]

The channel which is started.


## -returns



This callback function does not return a value.




## -remarks



After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelStarted</i>, by using the <a href="https://msdn.microsoft.com/2255C8A2-85FB-4B96-8AE9-66FAFD73EE73">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

If a paused channel is opened or an opened channel is started, Kernel Mode Client Library (KMCL) calls <i>EvtVmbChannelStarted</i> after it calls the <a href="https://msdn.microsoft.com/4E35AAA4-B9BA-4248-BBE6-FB576CAFD046">EvtVmbChannelOpened</a> callback.  <i>EvtVmbChannelStarted</i> can call the <a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>, <a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>, and <a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a> functions 
to queue up outgoing packets. Because the incoming queue is not running at this point, this callback must not block on incoming packets or 
completions.  

Most drivers using KMCL do not implement
this callback. An alternative is the <a href="https://msdn.microsoft.com/0F48459F-BA02-4A0E-9228-BC064A6AD150">EvtVmbChannelPostStarted</a> callback function.

Waiting for a sent packet to complete, such as by the <a href="https://msdn.microsoft.com/312DED8E-570E-4DEC-B084-36894970F49F">VmbChannelSendSynchronousRequest</a> function, never returns because packets are not flowing when this callback is invoked.




## -see-also




<a href="https://msdn.microsoft.com/4E35AAA4-B9BA-4248-BBE6-FB576CAFD046">EvtVmbChannelOpened</a>



<a href="https://msdn.microsoft.com/0F48459F-BA02-4A0E-9228-BC064A6AD150">EvtVmbChannelPostStarted</a>



<a href="https://msdn.microsoft.com/2255C8A2-85FB-4B96-8AE9-66FAFD73EE73">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/312DED8E-570E-4DEC-B084-36894970F49F">VmbChannelSendSynchronousRequest</a>



<a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>



<a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>



<a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a>
 

 

