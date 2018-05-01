---
UID: NF:vmbuskernelmodeclientlibapi.VmbServerChannelInitSetVmbusHandle
title: VmbServerChannelInitSetVmbusHandle function
author: windows-driver-content
description: The VmbServerChannelInitSetVmbusHandle function associates an instance of VMBus with this channel.
old-location: netvista\vmbserverchannelinitsetvmbushandle.htm
old-project: netvista
ms.assetid: 0ECF76C7-9475-439E-8E59-B2B7CD350D24
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbServerChannelInitSetVmbusHandle, VmbServerChannelInitSetVmbusHandle function [Network Drivers Starting with Windows Vista], netvista.vmbserverchannelinitsetvmbushandle, vmbuskernelmodeclientlibapi/VmbServerChannelInitSetVmbusHandle
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	VmbServerChannelInitSetVmbusHandle
product: Windows
targetos: Windows
req.typenames: 
---

# VmbServerChannelInitSetVmbusHandle function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbServerChannelInitSetVmbusHandle</b> function associates an instance of VMBus with this channel.  


## -parameters




### -param Channel [in]

A handle for a channel.


### -param VmbusHandle [in]

A kernel mode handle to the VMBus vdev of the partition.


## -remarks



The VMBus
instance was previously initialized for the specific guest virtual machine. Therefore, invoking this function identifies the child virtual machine to which this channel is offered.

 Obtain a value for the <i>VmbusHandle</i> parameter by using the <a href="https://msdn.microsoft.com/C549B9C7-221D-4DD8-9D8D-24BC729099C7">VmbConvertVmbusHandleToKernelHandle</a> function.


This function can be called while running in any thread context.




## -see-also




<a href="https://msdn.microsoft.com/C549B9C7-221D-4DD8-9D8D-24BC729099C7">VmbConvertVmbusHandleToKernelHandle</a>
 

 

