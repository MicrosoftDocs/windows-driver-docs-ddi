---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetClientContextSize
title: VmbChannelInitSetClientContextSize function
author: windows-driver-content
description: The VmbChannelInitSetClientContextSize function sets the size of the optional context area allocated for the client driver on each incoming packet.
old-location: netvista\vmbchannelinitsetclientcontextsize.htm
old-project: netvista
ms.assetid: 6AABB3EB-F61A-40DA-BA9F-2AB91FC4B89E
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.vmbchannelinitsetclientcontextsize, vmbuskernelmodeclientlibapi/VmbChannelInitSetClientContextSize, VmbChannelInitSetClientContextSize, VmbChannelInitSetClientContextSize function [Network Drivers Starting with Windows Vista]
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
-	VmbChannelInitSetClientContextSize
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelInitSetClientContextSize function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetClientContextSize</b> function sets the size of the optional context area allocated for the client driver
on each incoming packet.


## -syntax


````
NTSTATUS
 VmbChannelInitSetClientContextSize(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     ContextSize
);
````


## -parameters




### -param Channel [in]

A handle for a channel.


### -param ContextSize [in]

The size of the context area allocated on each packet     object.

