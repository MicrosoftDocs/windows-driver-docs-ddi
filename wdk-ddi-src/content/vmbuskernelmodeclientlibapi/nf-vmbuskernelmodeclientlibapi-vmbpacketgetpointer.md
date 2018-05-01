---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketGetPointer
title: VmbPacketGetPointer function
author: windows-driver-content
description: The VmbPacketGetPointer function retrieves a pointer that was previously saved by using the VmbPacketSetPointer function.
old-location: netvista\vmbpacketgetpointer.htm
old-project: netvista
ms.assetid: 56B9C623-2038-4DD3-AA1B-D9A6E47E06C1
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbPacketGetPointer, VmbPacketGetPointer function [Network Drivers Starting with Windows Vista], netvista.vmbpacketgetpointer, vmbuskernelmodeclientlibapi/VmbPacketGetPointer
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
-	VmbPacketGetPointer
product: Windows
targetos: Windows
req.typenames: 
---

# VmbPacketGetPointer function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketGetPointer</b> function retrieves a pointer that was previously
saved by using the <a href="https://msdn.microsoft.com/FFEBEBD0-1FF2-4F27-B028-051B117CA325">VmbPacketSetPointer</a> function.


## -parameters




### -param PacketObject [in]

The handle of a packet object.


## -returns



<b>VmbPacketGetPointer</b> returns the value previously saved by using <a href="https://msdn.microsoft.com/FFEBEBD0-1FF2-4F27-B028-051B117CA325">VmbPacketSetPointer</a>.




## -see-also




<a href="https://msdn.microsoft.com/FFEBEBD0-1FF2-4F27-B028-051B117CA325">VmbPacketSetPointer</a>
 

 

