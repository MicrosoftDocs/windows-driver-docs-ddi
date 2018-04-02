---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelCleanup
title: VmbChannelCleanup function
author: windows-driver-content
description: The VmbChannelCleanup function disposes of a channel that was allocated by using the VmbChannelAllocate function or initialized by using a VMBus channel initialization function.
old-location: netvista\vmbchannelcleanup.htm
old-project: netvista
ms.assetid: E079527D-1687-4A12-B86E-96C89CE458CE
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbChannelCleanup, VmbChannelCleanup function [Network Drivers Starting with Windows Vista], netvista.vmbchannelcleanup, vmbuskernelmodeclientlibapi/VmbChannelCleanup
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
-	VmbChannelCleanup
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelCleanup function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelCleanup</b> function disposes of a channel that was allocated by using the <a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a> function  or initialized by using a  VMBus channel initialization function. 


## -parameters




### -param Channel [in]

The channel to clean up. 


## -returns



This function does not return a value.




## -remarks



If the channel was allocated by <a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a>, <b>VmbChannelCleanup</b> also releases the channel. 

Before you call this function, the channel must be disabled.




## -see-also




<a href="https://msdn.microsoft.com/97169CF5-566E-4EF6-88AD-7B68E9FE46EC">VmbChannelAllocate</a>
 

 

