---
UID: NS:ks._KSPROCESSPIN
title: _KSPROCESSPIN
author: windows-driver-content
description: The KSPROCESSPIN structure describes the process state of a specific pin.
old-location: stream\ksprocesspin.htm
old-project: stream
ms.assetid: a1625eb2-a38b-4517-b873-f33b5ced8705
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _KSPROCESSPIN, *PKSPROCESSPIN, KSPROCESSPIN
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
req.alt-api: KSPROCESSPIN
req.alt-loc: ks.h
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
req.typenames: *PKSPROCESSPIN, KSPROCESSPIN
---

# _KSPROCESSPIN structure



## -description
The KSPROCESSPIN structure describes the process state of a specific pin.



## -syntax

````
typedef struct _KSPROCESSPIN {
  PKSPIN            Pin;
  PKSSTREAM_POINTER StreamPointer;
  PKSPROCESSPIN     InPlaceCounterpart;
  PKSPROCESSPIN     DelegateBranch;
  PKSPROCESSPIN     CopySource;
  PVOID             Data;
  ULONG             BytesAvailable;
  ULONG             BytesUsed;
  ULONG             Flags;
  BOOLEAN           Terminate;
} KSPROCESSPIN, *PKSPROCESSPIN;
````


## -struct-fields

### -field Pin

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure that the KSPROCESSPIN structure is describing. Everything in the structure refers to this KSPIN.


### -field StreamPointer

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure that points into the input stream at the current input location or into the output stream at the current output location. This can be used, for example, by output pins to stamp information onto the associated <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> (ProcessPin-&gt;StreamPointer-&gt;StreamHeader-&gt;Flags=...).


### -field InPlaceCounterpart

A pointer to a KSPROCESSPIN structure. If this KSPROCESSPIN is not part of an <a href="wdkgloss.i#wdkgloss.inplace#wdkgloss.inplace"><i>inplace</i></a> transform, AVStream sets <b>InPlaceCounterpart</b> to <b>NULL</b>. If this KSPROCESSPIN is the input to an inplace transform, <b>InPlaceCounterpart</b> points to the output process pin for the transform. If this KSPROCESSPIN is the output of an inplace transform, <b>InPlaceCounterpart</b> points to the input process pin for the transform.


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

This member contains a copy of the flags from the relevant <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> structure, if this KSPROCESSPIN is an input pin.


### -field Terminate

This member indicates whether the current data frame should be sent downstream after the process dispatch finishes. If <b>TRUE</b>, the frame is sent downstream even if all data has not been consumed. If <b>FALSE</b>, the frame is not released until all data is consumed.


## -remarks
The KSPROCESSPIN structure is used in the <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">filter-centric processing</a> model. You can use this structure to access data on a specific input pin or to write out processed data to an output pin.

Only filter-centric clients use process pins. Further, process pins that have a non-<b>NULL</b><b>DelegateBranch</b> or a non-<b>NULL</b><b>CopySource</b> typically are not of concern to the client. The splitter automatically handles process pins with these pointers.

Most clients are concerned with the members <b>Pin</b>, <b>Data</b>, <b>BytesAvailable</b>, <b>BytesUsed</b>, <b>Flags</b>, and <b>Terminate</b>. Data can be read from the stream or written into the stream through the <b>Data</b> member; <b>BytesAvailable</b> tells the client how many bytes of data are available in the current data frame (buffer) that <b>Data</b> points to. As the client minidriver reads from or writes to the stream, <b>BytesUsed</b> should be updated to reflect how many bytes of data have been consumed. The <b>Terminate</b> flag can be set if the minidriver is done with the current frame despite the fact that <b>BytesUsed</b> is not equal to <b>BytesAvailable</b>. After the minidriver exits the processing dispatch, pointers are advanced, and frames are completed as appropriate.


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-_ksprocesspin_indexentry.md">KSPROCESSPIN_INDEXENTRY</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROCESSPIN structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

