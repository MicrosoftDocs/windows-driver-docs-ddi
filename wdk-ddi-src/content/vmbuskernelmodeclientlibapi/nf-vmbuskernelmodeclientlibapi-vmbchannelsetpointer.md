---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSetPointer
title: VmbChannelSetPointer function
author: windows-driver-content
description: The VmbChannelSetPointer function saves an arbitrary pointer in a channel context.
old-location: netvista\vmbchannelsetpointer.htm
old-project: netvista
ms.assetid: E536B66D-EAF2-4377-8452-7D37A277E7C8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbChannelSetPointer, VmbChannelSetPointer function [Network Drivers Starting with Windows Vista], netvista.vmbchannelsetpointer, vmbuskernelmodeclientlibapi/VmbChannelSetPointer
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
-	VmbChannelSetPointer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelSetPointer function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSetPointer</b> function saves an arbitrary pointer in a channel
context.  


## -parameters




### -param Channel [in]

A handle for a channel.  


### -param Pointer [in, optional]

Arbitrary pointer to save in the channel's context.


## -returns



This function does not return a value.




## -remarks



  This is intended to be a more efficient way for a client driver to retrieve client driver's context.  For more information, see the <a href="https://msdn.microsoft.com/F3BEE6FB-51C5-4C3C-A831-3B7C06B3C14D">VmbChannelGetPointer</a> function.




## -see-also




<a href="https://msdn.microsoft.com/F3BEE6FB-51C5-4C3C-A831-3B7C06B3C14D">VmbChannelGetPointer</a>
 

 

