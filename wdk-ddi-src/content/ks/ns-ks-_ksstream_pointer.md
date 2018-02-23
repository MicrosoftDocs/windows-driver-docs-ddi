---
UID: NS:ks._KSSTREAM_POINTER
title: "_KSSTREAM_POINTER"
author: windows-driver-content
description: The KSSTREAM_POINTER structure is the basic AVStream pointer into a stream.
old-location: stream\ksstream_pointer.htm
old-project: stream
ms.assetid: 31cdb264-89a1-48dc-af0c-b18d4f077d0f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ks/KSSTREAM_POINTER, KSSTREAM_POINTER structure [Streaming Media Devices], *PKSSTREAM_POINTER, PKSSTREAM_POINTER, stream.ksstream_pointer, ks/PKSSTREAM_POINTER, avstruct_1856dc7a-3351-4a87-97a5-85b06d12ab30.xml, _KSSTREAM_POINTER, PKSSTREAM_POINTER structure pointer [Streaming Media Devices], KSSTREAM_POINTER
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSSTREAM_POINTER
product: Windows
targetos: Windows
req.typenames: "*PKSSTREAM_POINTER, KSSTREAM_POINTER"
---

# _KSSTREAM_POINTER structure


## -description


The KSSTREAM_POINTER structure is the basic AVStream pointer into a stream.


## -syntax


````
typedef struct _KSSTREAM_POINTER {
  PVOID                    Context;
  PKSPIN                   Pin;
  PKSSTREAM_HEADER         StreamHeader;
  PKSSTREAM_POINTER_OFFSET Offset;
  KSSTREAM_POINTER_OFFSET  OffsetIn;
  KSSTREAM_POINTER_OFFSET  OffsetOut;
} KSSTREAM_POINTER, *PKSSTREAM_POINTER;
````


## -struct-fields




### -field Context

A pointer to client-requested context information. The leading edge and trailing edge stream pointers have this member set to <b>NULL</b>. Cloned stream pointers can specify that they wish to have context information via the mechanism described in <a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>. 


### -field Pin

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure to which this stream pointer belongs.


### -field StreamHeader

A pointer to the stream header object for the data frame that this stream pointer currently points to. See <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> for more information.


### -field Offset

A pointer to a structure of type <a href="..\ks\ns-ks-_ksstream_pointer_offset.md">KSSTREAM_POINTER_OFFSET</a>. Points to either <b>OffsetIn</b> or <b>OffsetOut</b> depending on whether the pin to which this stream pointer belongs is an input pin or output pin.


### -field OffsetIn

This member specifies a structure of type <a href="..\ks\ns-ks-_ksstream_pointer_offset.md">KSSTREAM_POINTER_OFFSET</a> describing the data currently pointed to by the stream pointer.


### -field OffsetOut

This member specifies a structure of type <a href="..\ks\ns-ks-_ksstream_pointer_offset.md">KSSTREAM_POINTER_OFFSET</a>. Use this member to output data on an output pin.


## -remarks



A queue object for a stream has at minimum one hard-defined stream pointer: the leading-edge stream pointer. For more information, see <a href="https://msdn.microsoft.com/73ab974f-8034-421f-980a-2393d84ec54c">Leading and Trailing Edge Stream Pointers</a>.

For general information about stream pointers, see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also

<a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>



<a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>



<a href="..\ks\nf-ks-ksstreampointerdelete.md">KsStreamPointerDelete</a>



<a href="..\ks\nf-ks-ksstreampointeradvanceoffsets.md">KsStreamPointerAdvanceOffsets</a>



<a href="..\ks\nf-ks-ksstreampointeradvance.md">KsStreamPointerAdvance</a>



<a href="..\ks\nf-ks-ksstreampointeradvanceoffsetsandunlock.md">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="..\ks\nf-ks-ksstreampointerunlock.md">KsStreamPointerUnlock</a>



<a href="..\ks\ns-ks-_ksstream_pointer_offset.md">KSSTREAM_POINTER_OFFSET</a>



<a href="..\ks\nf-ks-ksstreampointerlock.md">KsStreamPointerLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSSTREAM_POINTER structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

