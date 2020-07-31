---
UID: NF:portcls.IMiniportMidiStream.Read
title: IMiniportMidiStream::Read (portcls.h)
description: The Read method reads data from an incoming MIDI stream.
old-location: audio\iminiportmidistream_read.htm
tech.root: audio
ms.assetid: 448dc408-c47f-4c8b-8baf-a831c69c3020
ms.date: 05/08/2018
keywords: ["IMiniportMidiStream::Read"]
ms.keywords: IMiniportMidiStream interface [Audio Devices],Read method, IMiniportMidiStream.Read, IMiniportMidiStream::Read, Read, Read method [Audio Devices], Read method [Audio Devices],IMiniportMidiStream interface, audio.iminiportmidistream_read, audmp-routines_35ce63a1-ab31-4758-887a-9043e1f65915.xml, portcls/IMiniportMidiStream::Read
f1_keywords:
 - "portcls/IMiniportMidiStream.Read"
 - "IMiniportMidiStream.Read"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportMidiStream.Read
targetos: Windows
req.typenames: 
---

# IMiniportMidiStream::Read


## -description


The <code>Read</code> method reads data from an incoming MIDI stream.


## -parameters




### -param BufferAddress [in]

Specifies the address of a caller-allocated buffer. The method copies the incoming MIDI data from the device to the buffer. The allocated size of this buffer must be greater than or equal to <i>BufferLength</i>.


### -param BufferLength [in]

Specifies the length in bytes of the buffer pointed to by <i>BufferAddress</i>.


### -param BytesRead [out]

Output pointer to a caller-allocated variable into which the method writes a count specifying the actual number of bytes successfully read from the device into the buffer.


## -returns



<code>Read</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Invalid device request (for example, calling <code>Read</code> on a MIDI output stream).

</td>
</tr>
</table>
 




## -remarks



The miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportmidi-notify">IPortMidi::Notify</a> to notify the port driver when incoming MIDI data becomes available from the capture device. The port driver calls <b>IMiniportMidi::Read</b> to retrieve the data. The port driver continues to call <code>Read</code> as long as more data is available.

The <code>Read</code> method returns STATUS_SUCCESS and a <i>BytesRead</i> count of zero to indicate that no more MIDI input data is currently available from the device. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportmidistream">IMiniportMidiStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportmidistream-write">IMiniportMidiStream::Write</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportmidi-notify">IPortMidi::Notify</a>
 

 

