---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketAllocate
title: VmbPacketAllocate function
author: windows-driver-content
description: The VmbPacketAllocate function allocates a packet from the channel's lookaside list.
old-location: netvista\vmbpacketallocate.htm
old-project: netvista
ms.assetid: F121A7BC-5504-4CF5-8C8A-0568D6C4F77F
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbPacketAllocate, VmbPacketAllocate function [Network Drivers Starting with Windows Vista], netvista.vmbpacketallocate, vmbuskernelmodeclientlibapi/VmbPacketAllocate
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
-	VmbPacketAllocate
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbPacketAllocate function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketAllocate</b> function allocates a packet from the channel's lookaside list.


## -parameters




### -param Channel [in]

A handle for a channel.  


## -returns



<b>VmbPacketAllocate</b> returns a pointer to an allocated VMBus packet object or null.




## -remarks



The default completion routine of a packet automatically releases the packet.
If the packet is not sent or if the completion routine is changed, the
client should call the <a href="https://msdn.microsoft.com/15688701-2385-4F17-A944-D398EEF3C277">VmbPacketFree</a> function to release the packet.




## -see-also




<a href="https://msdn.microsoft.com/15688701-2385-4F17-A944-D398EEF3C277">VmbPacketFree</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbPacketAllocate function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

