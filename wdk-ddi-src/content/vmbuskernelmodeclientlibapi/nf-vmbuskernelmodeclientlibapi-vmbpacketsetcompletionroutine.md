---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketSetCompletionRoutine
title: VmbPacketSetCompletionRoutine function
author: windows-driver-content
description: The VmbPacketSetCompletionRoutine function sets the completion routine for a packet object.
old-location: netvista\vmbpacketsetcompletionroutine.htm
old-project: netvista
ms.assetid: 5781FE16-6CC8-425B-B14D-C78901D81A75
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbPacketSetCompletionRoutine, VmbPacketSetCompletionRoutine function [Network Drivers Starting with Windows Vista], netvista.vmbpacketsetcompletionroutine, vmbuskernelmodeclientlibapi/VmbPacketSetCompletionRoutine
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
-	VmbPacketSetCompletionRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# VmbPacketSetCompletionRoutine function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSetCompletionRoutine</b> function sets the completion routine for a packet object.  


## -parameters




### -param PacketObject [in]

The packet for which to specify a completion routine.



### -param CompletionRoutine [in]

Function to call when the packet is completed.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/DEE6FBD6-4807-4216-9010-F59C9E08076B">EvtVmbPacketCompletionRoutine</a>



<a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>



<a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>



<a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a>
 

 

