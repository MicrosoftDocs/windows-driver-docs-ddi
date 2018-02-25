---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelUnmapGpadl
title: VmbChannelUnmapGpadl function
author: windows-driver-content
description: The VmbChannelUnmapGpadl function unmaps a Guest Physical Address Descriptor List (GPADL) mapped using by the VmbChannelMapGpadl function. The buffer must no longer be in use by the server before this function is called.
old-location: netvista\vmbchannelunmapgpadl.htm
old-project: netvista
ms.assetid: EE300158-D7D8-4353-B205-362232A22568
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, G, U, V, VmbChannelUnmapGpadl, VmbChannelUnmapGpadl function [Network Drivers Starting with Windows Vista], a, b, d, e, h, l, m, n, netvista.vmbchannelunmapgpadl, p, vmbuskernelmodeclientlibapi/VmbChannelUnmapGpadl"
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	VmbusKernelModeClientLibApi.h
apiname:
-	VmbChannelUnmapGpadl
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelUnmapGpadl function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelUnmapGpadl</b> function unmaps a Guest Physical Address Descriptor List (GPADL) mapped using by the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelmapgpadl.md">VmbChannelMapGpadl</a> function. The buffer must no longer be in
use by the server before this function is called.


## -syntax


````
VOID VmbChannelUnmapGpadl(
  _In_ VMBCHANNEL  Channel,
  _In_  UINT32    GpadlHandle
);
````


## -parameters




### -param Channel [in]

A handle for a channel.  


### -param GpadlHandle [in]

The handle of the GPADL to unmap.


## -returns



This function does not return a value.




## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelmapgpadl.md">VmbChannelMapGpadl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelUnmapGpadl function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

