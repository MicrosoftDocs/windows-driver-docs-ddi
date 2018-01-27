---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelCleanup
title: VmbChannelCleanup function
author: windows-driver-content
description: The VmbChannelCleanup function disposes of a channel that was allocated by using the VmbChannelAllocate function or initialized by using a VMBus channel initialization function.
old-location: netvista\vmbchannelcleanup.htm
old-project: netvista
ms.assetid: E079527D-1687-4A12-B86E-96C89CE458CE
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: VmbChannelCleanup, VmbChannelCleanup function [Network Drivers Starting with Windows Vista], vmbuskernelmodeclientlibapi/VmbChannelCleanup, netvista.vmbchannelcleanup
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
-	VmbChannelCleanup
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelCleanup function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelCleanup</b> function disposes of a channel that was allocated by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelallocate.md">VmbChannelAllocate</a> function  or initialized by using a  VMBus channel initialization function. 


## -syntax


````
VOID VmbChannelCleanup(
  _In_ __drv_freesMem(Mem) VMBCHANNEL Channel
    
);
````


## -parameters




### -param Channel [in]

The channel to clean up. 


## -returns


This function does not return a value.



## -remarks


If the channel was allocated by <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelallocate.md">VmbChannelAllocate</a>, <b>VmbChannelCleanup</b> also releases the channel. 

Before you call this function, the channel must be disabled.



## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelallocate.md">VmbChannelAllocate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelCleanup function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

