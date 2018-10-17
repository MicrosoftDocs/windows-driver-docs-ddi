---
UID: NS:ks._KSSTREAM_POINTER
title: "_KSSTREAM_POINTER"
author: windows-driver-content
description: The KSSTREAM_POINTER structure is the basic AVStream pointer into a stream.
old-location: stream\ksstream_pointer.htm
tech.root: stream
ms.assetid: 31cdb264-89a1-48dc-af0c-b18d4f077d0f
ms.date: 4/23/2018
ms.keywords: "*PKSSTREAM_POINTER, KSSTREAM_POINTER, KSSTREAM_POINTER structure [Streaming Media Devices], PKSSTREAM_POINTER, PKSSTREAM_POINTER structure pointer [Streaming Media Devices], _KSSTREAM_POINTER, avstruct_1856dc7a-3351-4a87-97a5-85b06d12ab30.xml, ks/KSSTREAM_POINTER, ks/PKSSTREAM_POINTER, stream.ksstream_pointer"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	ks.h
api_name:
-	KSSTREAM_POINTER
product:
- Windows
targetos: Windows
req.typenames: KSSTREAM_POINTER, *PKSSTREAM_POINTER
---

# _KSSTREAM_POINTER structure


## -description


The KSSTREAM_POINTER structure is the basic AVStream pointer into a stream.


## -struct-fields




### -field Context

A pointer to client-requested context information. The leading edge and trailing edge stream pointers have this member set to <b>NULL</b>. Cloned stream pointers can specify that they wish to have context information via the mechanism described in <a href="https://msdn.microsoft.com/library/windows/hardware/dn892389">KsStreamPointerClone</a>. 


### -field Pin

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure to which this stream pointer belongs.


### -field StreamHeader

A pointer to the stream header object for the data frame that this stream pointer currently points to. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a> for more information.


### -field Offset

A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567140">KSSTREAM_POINTER_OFFSET</a>. Points to either <b>OffsetIn</b> or <b>OffsetOut</b> depending on whether the pin to which this stream pointer belongs is an input pin or output pin.


### -field OffsetIn

This member specifies a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567140">KSSTREAM_POINTER_OFFSET</a> describing the data currently pointed to by the stream pointer.


### -field OffsetOut

This member specifies a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567140">KSSTREAM_POINTER_OFFSET</a>. Use this member to output data on an output pin.


## -remarks



A queue object for a stream has at minimum one hard-defined stream pointer: the leading-edge stream pointer. For more information, see <a href="https://msdn.microsoft.com/73ab974f-8034-421f-980a-2393d84ec54c">Leading and Trailing Edge Stream Pointers</a>.

For general information about stream pointers, see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567140">KSSTREAM_POINTER_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567125">KsStreamPointerAdvance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567126">KsStreamPointerAdvanceOffsets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567127">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892389">KsStreamPointerClone</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567130">KsStreamPointerDelete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892390">KsStreamPointerLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567137">KsStreamPointerUnlock</a>
 

 

