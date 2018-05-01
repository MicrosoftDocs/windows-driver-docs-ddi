---
UID: NS:strmini._HW_STREAM_OBJECT
title: "_HW_STREAM_OBJECT"
author: windows-driver-content
description: HW_STREAM_OBJECT describes an instance of a minidriver stream.
old-location: stream\hw_stream_object.htm
old-project: stream
ms.assetid: 0cb2041a-844d-4ddb-9dab-e1c77c28835a
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PHW_STREAM_OBJECT, HW_STREAM_OBJECT, HW_STREAM_OBJECT structure [Streaming Media Devices], PHW_STREAM_OBJECT, PHW_STREAM_OBJECT structure pointer [Streaming Media Devices], _HW_STREAM_OBJECT, strclass-struct_c409633a-dccd-4f70-a412-0da08feeae43.xml, stream.hw_stream_object, strmini/HW_STREAM_OBJECT, strmini/PHW_STREAM_OBJECT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
-	strmini.h
api_name:
-	HW_STREAM_OBJECT
product: Windows
targetos: Windows
req.typenames: HW_STREAM_OBJECT, *PHW_STREAM_OBJECT
---

# _HW_STREAM_OBJECT structure


## -description


HW_STREAM_OBJECT describes an instance of a minidriver stream.


## -struct-fields




### -field SizeOfThisPacket

Specifies the size, in bytes, of this structure.


### -field StreamNumber

Specifies the offset of the stream within the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559686">HW_STREAM_DESCRIPTOR</a> structure.


### -field HwStreamExtension

Points to the stream extension, a buffer allocated by the class driver for the minidriver to use to hold private information about this stream. The minidriver sets the size of the buffer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself with the stream class driver.


### -field ReceiveDataPacket

Pointer to the stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568470">StrMiniReceiveStreamDataPacket</a> routine.


### -field ReceiveControlPacket

Pointer to the stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568467">StrMiniReceiveStreamControlPacket</a> routine.


### -field HwClockObject

Contains the stream's clock object. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff559671">HW_CLOCK_OBJECT</a> for details.


### -field Dma

If <b>TRUE</b>, the device uses DMA to transfer data for this stream.


### -field Pio

If <b>TRUE</b>, the device uses programmed I/O to transfer data for this stream. Note that both the <b>Pio</b> and <b>Dma</b> members may be <b>TRUE</b>.


### -field HwDeviceExtension

Pointer to the minidriver's device extension. The minidriver may use this buffer to record private information. The minidriver sets the size of this buffer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver also passes pointers to this buffer in the <b>HwDeviceExtension</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559706">HW_TIME_CONTEXT</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -field StreamHeaderMediaSpecific

Specifies the size in bytes of the media-specific, per-stream header extension.


### -field StreamHeaderWorkspace

Specifies the size of the per-stream-header workspace.


### -field Allocator

Specifies <b>TRUE</b> if the driver uses allocators. Most minidrivers set this value to <b>FALSE</b>. 


### -field HwEventRoutine

Pointer to the stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568457">StrMiniEvent</a> routine


### -field Reserved

Reserved for system use. Do not use.


## -remarks



This structure is created by the class driver to hold information about a particular stream in the minidriver. For each stream-specific request, the class driver passes the HW_STREAM_OBJECT for the stream in the <b>StreamObject</b> member of the stream request block (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a>). 

When the class driver opens the stream and issues the SRB_OPEN_STREAM request to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a> routine, the minidriver initializes the stream object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559671">HW_CLOCK_OBJECT</a>
 

 

