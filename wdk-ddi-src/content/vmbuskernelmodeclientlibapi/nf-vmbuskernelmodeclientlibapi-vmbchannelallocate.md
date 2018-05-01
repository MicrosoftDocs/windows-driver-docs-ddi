---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelAllocate
title: VmbChannelAllocate function
author: windows-driver-content
description: The VmbChannelAllocate function allocates a new VMBus channel that has default parameters and callbacks.
old-location: netvista\vmbchannelallocate.htm
old-project: netvista
ms.assetid: 97169CF5-566E-4EF6-88AD-7B68E9FE46EC
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbChannelAllocate, VmbChannelAllocate function [Network Drivers Starting with Windows Vista], netvista.vmbchannelallocate, vmbuskernelmodeclientlibapi/VmbChannelAllocate
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbChannelAllocate
product: Windows
targetos: Windows
req.typenames: 
---

# VmbChannelAllocate function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

 The <b>VmbChannelAllocate</b> function allocates a new VMBus channel that has default parameters and callbacks. 


## -parameters




### -param ParentDeviceObject [in]

A pointer to the parent device.



### -param IsServer [in]

Whether the new channel is a server endpoint.



### -param Channel [out]

A pointer to an allocated channel.


## -remarks



The
channel may be further initialized using the VMBus channel initialization routines before
it is enabled by using the  <a href="https://msdn.microsoft.com/A0256B3F-C35C-45AB-A825-0A82189F08DC">VmbChannelEnable</a> function. The channel must be freed by using the <a href="https://msdn.microsoft.com/E079527D-1687-4A12-B86E-96C89CE458CE">VmbChannelCleanup</a> function.




## -see-also




<a href="https://msdn.microsoft.com/E079527D-1687-4A12-B86E-96C89CE458CE">VmbChannelCleanup</a>



<a href="https://msdn.microsoft.com/A0256B3F-C35C-45AB-A825-0A82189F08DC">VmbChannelEnable</a>
 

 

