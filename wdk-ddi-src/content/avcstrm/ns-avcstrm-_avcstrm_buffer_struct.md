---
UID: NS:avcstrm._AVCSTRM_BUFFER_STRUCT
title: _AVCSTRM_BUFFER_STRUCT
author: windows-driver-content
description: The AVCSTRM_BUFFER_STRUCT structure describes a buffer to be submitted to avcstrm.sys for read or write operations.
old-location: stream\avcstrm_buffer_struct.htm
old-project: stream
ms.assetid: ed9a5391-135d-4ac2-8b72-6a92d3ff9998
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _AVCSTRM_BUFFER_STRUCT, AVCSTRM_BUFFER_STRUCT, *PAVCSTRM_BUFFER_STRUCT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVCSTRM_BUFFER_STRUCT
req.alt-loc: avcstrm.h
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
req.typenames: AVCSTRM_BUFFER_STRUCT, *PAVCSTRM_BUFFER_STRUCT
---

# _AVCSTRM_BUFFER_STRUCT structure



## -description
The AVCSTRM_BUFFER_STRUCT structure describes a buffer to be submitted to <i>avcstrm.sys</i> for read or write operations.



## -syntax

````
typedef struct _AVCSTRM_BUFFER_STRUCT {
  BOOL             ClockProvider;
  HANDLE           ClockHandle;
  PKSSTREAM_HEADER StreamHeader;
  PVOID            FrameBuffer;
  PVOID            Context;
} AVCSTRM_BUFFER_STRUCT, *PAVCSTRM_BUFFER_STRUCT;
````


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVCSTRM_BUFFER_STRUCT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

