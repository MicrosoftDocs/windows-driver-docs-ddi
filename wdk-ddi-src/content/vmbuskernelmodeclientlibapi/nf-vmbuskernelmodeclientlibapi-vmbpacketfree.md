---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketFree
title: VmbPacketFree function
author: windows-driver-content
description: The VmbPacketFree function releases a packet allocated by using the VmbPacketAllocate function.
old-location: netvista\vmbpacketfree.htm
old-project: netvista
ms.assetid: 15688701-2385-4F17-A944-D398EEF3C277
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: VmbPacketFree function [Network Drivers Starting with Windows Vista], netvista.vmbpacketfree, vmbuskernelmodeclientlibapi/VmbPacketFree, VmbPacketFree
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
-	VmbPacketFree
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbPacketFree function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketFree</b> function releases a packet allocated by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md">VmbPacketAllocate</a> function.


## -syntax


````
VOID VmbPacketFree(
  _In_ __drv_freesMem(Mem) VMBPACKET VmbPacket
);
````


## -parameters




### -param VmbPacket [in]

 A pointer to an allocated VMBus packet object.


## -returns



This function does not return a value.




## -see-also

<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketallocate.md">VmbPacketAllocate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbPacketFree function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

