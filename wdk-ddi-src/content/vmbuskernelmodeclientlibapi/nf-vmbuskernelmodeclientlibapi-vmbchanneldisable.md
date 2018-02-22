---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelDisable
title: VmbChannelDisable function
author: windows-driver-content
description: The VmbChannelDisable function disables a channel, which closes it for client channels and revokes the channel offer for server channels. This function waits until the channel is completely torn down before it returns.
old-location: netvista\vmbchanneldisable.htm
old-project: netvista
ms.assetid: 688A1DF3-F801-47C3-8403-9FA5D96BD428
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: VmbChannelDisable, VmbChannelDisable function [Network Drivers Starting with Windows Vista], vmbuskernelmodeclientlibapi/VmbChannelDisable, netvista.vmbchanneldisable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	vmbkmcl.lib
-	vmbkmcl.dll
apiname:
-	VmbChannelDisable
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelDisable function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelDisable</b> function disables a channel, which closes it for client channels and revokes the channel offer for server channels. This function waits until the channel is completely torn down
before it returns.


## -syntax


````
VOID VmbChannelDisable(
  _In_ VMBCHANNEL Channel
);
````


## -parameters




### -param Channel [in]

The handle of a channel to disable.


## -returns



This function does not return a value.



