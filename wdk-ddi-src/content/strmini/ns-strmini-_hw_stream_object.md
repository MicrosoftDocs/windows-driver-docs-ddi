---
UID: NS:strmini._HW_STREAM_OBJECT
title: "_HW_STREAM_OBJECT"
author: windows-driver-content
description: HW_STREAM_OBJECT describes an instance of a minidriver stream.
old-location: stream\hw_stream_object.htm
old-project: stream
ms.assetid: 0cb2041a-844d-4ddb-9dab-e1c77c28835a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: HW_STREAM_OBJECT structure [Streaming Media Devices], HW_STREAM_OBJECT, PHW_STREAM_OBJECT structure pointer [Streaming Media Devices], strmini/PHW_STREAM_OBJECT, stream.hw_stream_object, _HW_STREAM_OBJECT, strmini/HW_STREAM_OBJECT, PHW_STREAM_OBJECT, *PHW_STREAM_OBJECT, strclass-struct_c409633a-dccd-4f70-a412-0da08feeae43.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	strmini.h
apiname:
-	HW_STREAM_OBJECT
product: Windows
targetos: Windows
req.typenames: "*PHW_STREAM_OBJECT, HW_STREAM_OBJECT"
req.product: Windows 10 or later.
---

# _HW_STREAM_OBJECT structure


## -description


HW_STREAM_OBJECT describes an instance of a minidriver stream.


## -syntax


````
typedef struct _HW_STREAM_OBJECT {
  ULONG                          SizeOfThisPacket;
  ULONG                          StreamNumber;
  PVOID                          HwStreamExtension;
  PHW_RECEIVE_STREAM_DATA_SRB    ReceiveDataPacket;
  PHW_RECEIVE_STREAM_CONTROL_SRB ReceiveControlPacket;
  HW_CLOCK_OBJECT                HwClockObject;
  BOOLEAN                        Dma;
  BOOLEAN                        Pio;
  PVOID                          HwDeviceExtension;
  ULONG                          StreamHeaderMediaSpecific;
  ULONG                          StreamHeaderWorkspace;
  BOOLEAN                        Allocator;
  PHW_EVENT_ROUTINE              HwEventRoutine;
  ULONG                          Reserved[2];
} HW_STREAM_OBJECT, *PHW_STREAM_OBJECT;
````


## -struct-fields




#### - SizeOfThisPacket

Specifies the size, in bytes, of this structure.


#### - StreamNumber

Specifies the offset of the stream within the minidriver's <a href="..\strmini\ns-strmini-_hw_stream_descriptor.md">HW_STREAM_DESCRIPTOR</a> structure.


#### - HwStreamExtension

Points to the stream extension, a buffer allocated by the class driver for the minidriver to use to hold private information about this stream. The minidriver sets the size of the buffer in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself with the stream class driver.


#### - ReceiveDataPacket

Pointer to the stream's <a href="..\strmini\nc-strmini-phw_receive_device_srb.md">StrMiniReceiveStreamDataPacket</a> routine.


#### - ReceiveControlPacket

Pointer to the stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568467">StrMiniReceiveStreamControlPacket</a> routine.


#### - HwClockObject

Contains the stream's clock object. See <a href="..\strmini\ns-strmini-_hw_clock_object.md">HW_CLOCK_OBJECT</a> for details.


#### - Dma

If <b>TRUE</b>, the device uses DMA to transfer data for this stream.


#### - Pio

If <b>TRUE</b>, the device uses programmed I/O to transfer data for this stream. Note that both the <b>Pio</b> and <b>Dma</b> members may be <b>TRUE</b>.


#### - HwDeviceExtension

Pointer to the minidriver's device extension. The minidriver may use this buffer to record private information. The minidriver sets the size of this buffer in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver also passes pointers to this buffer in the <b>HwDeviceExtension</b> member of the <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a>, <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>, and <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


#### - StreamHeaderMediaSpecific

Specifies the size in bytes of the media-specific, per-stream header extension.


#### - StreamHeaderWorkspace

Specifies the size of the per-stream-header workspace.


#### - Allocator

Specifies <b>TRUE</b> if the driver uses allocators. Most minidrivers set this value to <b>FALSE</b>. 


#### - HwEventRoutine

Pointer to the stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568457">StrMiniEvent</a> routine


#### - Reserved

Reserved for system use. Do not use.


## -remarks


This structure is created by the class driver to hold information about a particular stream in the minidriver. For each stream-specific request, the class driver passes the HW_STREAM_OBJECT for the stream in the <b>StreamObject</b> member of the stream request block (See <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a>). 

When the class driver opens the stream and issues the SRB_OPEN_STREAM request to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a> routine, the minidriver initializes the stream object.



## -see-also

<a href="..\strmini\ns-strmini-_hw_clock_object.md">HW_CLOCK_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20HW_STREAM_OBJECT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

