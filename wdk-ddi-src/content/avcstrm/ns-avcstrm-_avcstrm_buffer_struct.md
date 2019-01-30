---
UID: NS:avcstrm._AVCSTRM_BUFFER_STRUCT
title: "_AVCSTRM_BUFFER_STRUCT" (avcstrm.h)
description: The AVCSTRM_BUFFER_STRUCT structure describes a buffer to be submitted to avcstrm.sys for read or write operations.
old-location: stream\avcstrm_buffer_struct.htm
tech.root: stream
ms.assetid: ed9a5391-135d-4ac2-8b72-6a92d3ff9998
ms.date: 04/23/2018
ms.keywords: "*PAVCSTRM_BUFFER_STRUCT, AVCSTRM_BUFFER_STRUCT, AVCSTRM_BUFFER_STRUCT structure [Streaming Media Devices], PAVCSTRM_BUFFER_STRUCT, PAVCSTRM_BUFFER_STRUCT structure pointer [Streaming Media Devices], _AVCSTRM_BUFFER_STRUCT, avcsref_9cec2cfb-d187-4349-b443-894f881f5108.xml, avcstrm/AVCSTRM_BUFFER_STRUCT, avcstrm/PAVCSTRM_BUFFER_STRUCT, stream.avcstrm_buffer_struct"
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
-	avcstrm.h
api_name:
-	AVCSTRM_BUFFER_STRUCT
product:
- Windows
targetos: Windows
req.typenames: AVCSTRM_BUFFER_STRUCT, *PAVCSTRM_BUFFER_STRUCT
---

# _AVCSTRM_BUFFER_STRUCT structure


## -description


The AVCSTRM_BUFFER_STRUCT structure describes a buffer to be submitted to <i>avcstrm.sys</i> for read or write operations.


## -struct-fields




### -field ClockProvider

Indicates whether the subunit driver itself serves as a clock provider. This is <b>TRUE</b> if this stream also serves as a clock provider, Otherwise, this is <b>FALSE</b>.


### -field ClockHandle

Specifies a handle to a clock provider other than the subunit driver itself.


### -field StreamHeader

Pointer to a kernel streaming header that describes a packet of data to be read from or written to a streaming driver pin.


### -field FrameBuffer

Pointer to a nonpaged system-space virtual address for the buffer described by the MDL.


### -field Context

Pointer to a client context value.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a>
 

 

