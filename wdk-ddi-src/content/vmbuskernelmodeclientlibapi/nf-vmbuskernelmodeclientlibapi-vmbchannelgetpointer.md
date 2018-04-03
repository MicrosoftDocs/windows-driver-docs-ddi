---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelGetPointer
title: VmbChannelGetPointer function
author: windows-driver-content
description: The VmbChannelGetPointer function lets a client driver retrieve a pointer that was previously saved by using the VmbPacketSetPointer function.
old-location: netvista\vmbchannelgetpointer.htm
old-project: netvista
ms.assetid: F3BEE6FB-51C5-4C3C-A831-3B7C06B3C14D
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbChannelGetPointer, VmbChannelGetPointer function [Network Drivers Starting with Windows Vista], netvista.vmbchannelgetpointer, vmbuskernelmodeclientlibapi/VmbChannelGetPointer
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
-	VmbChannelGetPointer
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelGetPointer function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelGetPointer</b> function lets a client driver retrieve a pointer that was previously saved by using the  <a href="https://msdn.microsoft.com/FFEBEBD0-1FF2-4F27-B028-051B117CA325">VmbPacketSetPointer</a> function.


## -parameters




### -param Channel [in]

A handle for a channel.  


## -returns



The value previously saved by using <a href="https://msdn.microsoft.com/FFEBEBD0-1FF2-4F27-B028-051B117CA325">VmbPacketSetPointer</a>.




## -see-also




<a href="https://msdn.microsoft.com/FFEBEBD0-1FF2-4F27-B028-051B117CA325">VmbPacketSetPointer</a>
 

 

