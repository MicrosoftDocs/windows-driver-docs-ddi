---
UID: NF:portcls.IMiniportMidiStream.Write
title: IMiniportMidiStream::Write
author: windows-driver-content
description: The Write method writes data to an outgoing MIDI stream.
old-location: audio\iminiportmidistream_write.htm
old-project: audio
ms.assetid: 6ff4e4d7-3ba4-4e4b-98fa-62f269aee69f
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportMidiStream interface [Audio Devices],Write method, IMiniportMidiStream.Write, IMiniportMidiStream::Write, Write, Write method [Audio Devices], Write method [Audio Devices],IMiniportMidiStream interface, audio.iminiportmidistream_write, audmp-routines_523fd287-5380-4259-ba2c-4d9adef4fe4b.xml, portcls/IMiniportMidiStream::Write
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportMidiStream.Write
product: Windows
targetos: Windows
req.typenames: 
---

# IMiniportMidiStream::Write


## -description


The <code>Write</code> method writes data to an outgoing MIDI stream.


## -parameters




### -param BufferAddress [in]

Pointer to a caller-allocated buffer that contains the outgoing MIDI data


### -param BytesToWrite [in]

Specifies the number of bytes of MIDI data contained in the buffer that <i>BufferAddress</i> points to.


### -param BytesWritten [out]

Output pointer to a caller-allocated variable into which the method writes a count specifying the actual number of bytes that the method succeeded in writing to the MIDI output device. For more information, see the following Remarks section.


## -returns



<code>Write</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_DEVICE_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The call failed due to a device error.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Invalid device request (for example, calling <code>Write</code> on a MIDI input stream).

</td>
</tr>
</table>
 




## -remarks



If the method succeeds, it outputs one of the following values to the caller through the <i>BytesWritten</i> parameter:

<ul>
<li>
The same value as <i>BytesToWrite</i>. This value indicates that the method succeeded in writing all <i>BytesToWrite</i> bytes of data to the device.

</li>
<li>
A multiple of four that is less than <i>BytesToWrite</i>. If the method is able to write some but not all of the caller's data to the device, it should write a number of bytes that is a multiple of four. This value indicates that the caller should make another call to the method to write the remaining data.

</li>
<li>
Zero. This value indicates that the device is too busy to write any of the caller's data during the current call, but that the caller should try again later. The miniport driver is responsible for distinguishing a busy device from a device error. The method should avoid generating an endless succession of calls that always return success but write zero bytes.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536704">IMiniportMidiStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536705">IMiniportMidiStream::Read</a>
 

 

