---
UID: NS:strmini._HW_STREAM_OBJECT
title: _HW_STREAM_OBJECT (strmini.h)
description: HW_STREAM_OBJECT describes an instance of a minidriver stream.
old-location: stream\hw_stream_object.htm
tech.root: stream
ms.assetid: 0cb2041a-844d-4ddb-9dab-e1c77c28835a
ms.date: 04/23/2018
ms.keywords: "*PHW_STREAM_OBJECT, HW_STREAM_OBJECT, HW_STREAM_OBJECT structure [Streaming Media Devices], PHW_STREAM_OBJECT, PHW_STREAM_OBJECT structure pointer [Streaming Media Devices], _HW_STREAM_OBJECT, strclass-struct_c409633a-dccd-4f70-a412-0da08feeae43.xml, stream.hw_stream_object, strmini/HW_STREAM_OBJECT, strmini/PHW_STREAM_OBJECT"
ms.topic: struct
f1_keywords:
 - "strmini/HW_STREAM_OBJECT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- strmini.h
api_name:
- HW_STREAM_OBJECT
product:
- Windows
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

Specifies the offset of the stream within the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_descriptor">HW_STREAM_DESCRIPTOR</a> structure.


### -field HwStreamExtension

Points to the stream extension, a buffer allocated by the class driver for the minidriver to use to hold private information about this stream. The minidriver sets the size of the buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself with the stream class driver.


### -field ReceiveDataPacket

Pointer to the stream's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveStreamDataPacket</a> routine.


### -field ReceiveControlPacket

Pointer to the stream's <a href="https://docs.microsoft.com/previous-versions/ff568467(v=vs.85)">StrMiniReceiveStreamControlPacket</a> routine.


### -field HwClockObject

Contains the stream's clock object. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_clock_object">HW_CLOCK_OBJECT</a> for details.


### -field Dma

If <b>TRUE</b>, the device uses DMA to transfer data for this stream.


### -field Pio

If <b>TRUE</b>, the device uses programmed I/O to transfer data for this stream. Note that both the <b>Pio</b> and <b>Dma</b> members may be <b>TRUE</b>.


### -field HwDeviceExtension

Pointer to the minidriver's device extension. The minidriver may use this buffer to record private information. The minidriver sets the size of this buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>. The class driver also passes pointers to this buffer in the <b>HwDeviceExtension</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -field StreamHeaderMediaSpecific

Specifies the size in bytes of the media-specific, per-stream header extension.


### -field StreamHeaderWorkspace

Specifies the size of the per-stream-header workspace.


### -field Allocator

Specifies <b>TRUE</b> if the driver uses allocators. Most minidrivers set this value to <b>FALSE</b>. 


### -field HwEventRoutine

Pointer to the stream's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_event_routine">StrMiniEvent</a> routine


### -field Reserved

Reserved for system use. Do not use.


## -remarks



This structure is created by the class driver to hold information about a particular stream in the minidriver. For each stream-specific request, the class driver passes the HW_STREAM_OBJECT for the stream in the <b>StreamObject</b> member of the stream request block (See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>). 

When the class driver opens the stream and issues the SRB_OPEN_STREAM request to the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveDevicePacket</a> routine, the minidriver initializes the stream object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_clock_object">HW_CLOCK_OBJECT</a>
 

 

