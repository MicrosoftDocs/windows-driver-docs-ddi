---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetFriendlyName
title: VmbChannelInitSetFriendlyName function
author: windows-driver-content
description: The VmbChannelInitSetFriendlyName function sets the friendly name of the Kernel Mode Client Library (KMCL) channel. The friendly name is used for debugging and performance counter instance naming.
old-location: netvista\vmbchannelinitsetfriendlyname.htm
old-project: netvista
ms.assetid: 17FEFFDB-DCCC-4782-9F99-195A03F4901E
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbChannelInitSetFriendlyName, VmbChannelInitSetFriendlyName function [Network Drivers Starting with Windows Vista], netvista.vmbchannelinitsetfriendlyname, vmbuskernelmodeclientlibapi/VmbChannelInitSetFriendlyName
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbChannelInitSetFriendlyName
product:
- Windows
targetos: Windows
req.typenames: 
---

# VmbChannelInitSetFriendlyName function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetFriendlyName</b> function sets the friendly name of the Kernel Mode Client Library (KMCL) channel.  The friendly name is used for debugging and
performance counter instance naming.  


## -parameters




### -param Channel [in]

A handle for the channel to name.



### -param Name [in]

The new friendly name of the channel.


## -remarks



Channel names should be descriptive, yet
relatively short and easy to understand, for example, Network, SCSI, IDE, or SynthVideo.



