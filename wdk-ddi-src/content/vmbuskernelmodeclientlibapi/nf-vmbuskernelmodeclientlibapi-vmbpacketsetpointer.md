---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketSetPointer
title: VmbPacketSetPointer function
author: windows-driver-content
description: The VmbPacketSetPointer function saves an arbitrary pointer in the packet context.
old-location: netvista\vmbpacketsetpointer.htm
old-project: netvista
ms.assetid: FFEBEBD0-1FF2-4F27-B028-051B117CA325
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: VmbPacketSetPointer function [Network Drivers Starting with Windows Vista], VmbPacketSetPointer, netvista.vmbpacketsetpointer, vmbuskernelmodeclientlibapi/VmbPacketSetPointer
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
-	VmbPacketSetPointer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbPacketSetPointer function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSetPointer</b> function saves an arbitrary pointer in the packet
context.  


## -syntax


````
VOID VmbPacketSetPointer(
  _In_     VMBPACKET PacketObject,
  _In_opt_ PVOID     Pointer
);
````


## -parameters




### -param PacketObject [in]

A handle for a VMBus packet.


### -param Pointer [in, optional]

 An arbitrary pointer to save in the context of the packet.


## -returns



This function does not return a value.




## -remarks



This function is intended to offer a more efficient way to retrieve the context of a client driver.



