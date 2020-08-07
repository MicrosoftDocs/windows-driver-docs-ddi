---
UID: NS:ks._KSPROCESSPIN
title: _KSPROCESSPIN (ks.h)
description: The KSPROCESSPIN structure describes the process state of a specific pin.
old-location: stream\ksprocesspin.htm
tech.root: stream
ms.assetid: a1625eb2-a38b-4517-b873-f33b5ced8705
ms.date: 04/23/2018
keywords: ["KSPROCESSPIN structure"]
ms.keywords: "*PKSPROCESSPIN, KSPROCESSPIN, KSPROCESSPIN structure [Streaming Media Devices], PKSPROCESSPIN, PKSPROCESSPIN structure pointer [Streaming Media Devices], _KSPROCESSPIN, avstruct_a374bc58-a61f-4d3b-9b20-de14b7cc423f.xml, ks/KSPROCESSPIN, ks/PKSPROCESSPIN, stream.ksprocesspin"
f1_keywords:
 - "ks/KSPROCESSPIN"
 - "KSPROCESSPIN"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSPROCESSPIN
targetos: Windows
req.typenames: KSPROCESSPIN, *PKSPROCESSPIN
---

# _KSPROCESSPIN structure


## -description


The KSPROCESSPIN structure describes the process state of a specific pin.


## -struct-fields




### -field Pin

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure that the KSPROCESSPIN structure is describing. Everything in the structure refers to this KSPIN.


### -field StreamPointer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure that points into the input stream at the current input location or into the output stream at the current output location. This can be used, for example, by output pins to stamp information onto the associated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> (ProcessPin->StreamPointer->StreamHeader->Flags=...).


### -field InPlaceCounterpart

A pointer to a KSPROCESSPIN structure. If this KSPROCESSPIN is not part of an <a href="https://docs.microsoft.com/windows-hardware/drivers/">inplace</a> transform, AVStream sets <b>InPlaceCounterpart</b> to <b>NULL</b>. If this KSPROCESSPIN is the input to an inplace transform, <b>InPlaceCounterpart</b> points to the output process pin for the transform. If this KSPROCESSPIN is the output of an inplace transform, <b>InPlaceCounterpart</b> points to the input process pin for the transform.


### -field DelegateBranch

A pointer to a KSPROCESSPIN structure. If frames coming out of this KSPROCESSPIN are being split and sent to multiple sink pins, and the split does not cause a data copy (that is, the split sends the frames in a read-only manner and all of the split pin instances are in the same pipe), <b>DelegateBranch</b> points to the first instance of the process pin. The splitter automatically handles any process pin that has a non-<b>NULL</b><b>DelegateBranch</b>.


### -field CopySource

A pointer to a KSPROCESSPIN structure. If frames coming out of this process pin are being split and sent to multiple sink pins in a manner that causes a data copy (that is, one of the downstream filters is modifying the data frame by using an in-place transform), <b>CopySource</b> points to the process pin from which the frame was copied. The splitter automatically handles any process pin that has a non-<b>NULL</b><b>CopySource</b>.


### -field Data

A pointer to a buffer. If the pin described by this process entry is an input pin, <b>Data</b> points to the next available byte of data to be input. If the pin described by this process entry is an output pin, <b>Data</b> points to an output buffer in which processed data is placed.


### -field BytesAvailable

This member specifies how many bytes of data are available in <b>Data</b>.


### -field BytesUsed

This member specifies how many bytes of this data frame have been used by the process function. AVStream drivers should set this member to update how much they have read or written.


### -field Flags

This member contains a copy of the flags from the relevant <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> structure, if this KSPROCESSPIN is an input pin.


### -field Terminate

This member indicates whether the current data frame should be sent downstream after the process dispatch finishes. If <b>TRUE</b>, the frame is sent downstream even if all data has not been consumed. If <b>FALSE</b>, the frame is not released until all data is consumed.


## -remarks



The KSPROCESSPIN structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">filter-centric processing</a> model. You can use this structure to access data on a specific input pin or to write out processed data to an output pin.

Only filter-centric clients use process pins. Further, process pins that have a non-<b>NULL</b><b>DelegateBranch</b> or a non-<b>NULL</b><b>CopySource</b> typically are not of concern to the client. The splitter automatically handles process pins with these pointers.

Most clients are concerned with the members <b>Pin</b>, <b>Data</b>, <b>BytesAvailable</b>, <b>BytesUsed</b>, <b>Flags</b>, and <b>Terminate</b>. Data can be read from the stream or written into the stream through the <b>Data</b> member; <b>BytesAvailable</b> tells the client how many bytes of data are available in the current data frame (buffer) that <b>Data</b> points to. As the client minidriver reads from or writes to the stream, <b>BytesUsed</b> should be updated to reflect how many bytes of data have been consumed. The <b>Terminate</b> flag can be set if the minidriver is done with the current frame despite the fact that <b>BytesUsed</b> is not equal to <b>BytesAvailable</b>. After the minidriver exits the processing dispatch, pointers are advanced, and frames are completed as appropriate.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin_indexentry">KSPROCESSPIN_INDEXENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a>
 

 

