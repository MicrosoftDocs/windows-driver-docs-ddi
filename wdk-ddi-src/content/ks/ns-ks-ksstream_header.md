---
UID: NS:ks.__unnamed_struct_47
title: KSSTREAM_HEADER
author: windows-driver-content
description: The KSSTREAM_HEADER structure is a variable-length structure that describes a packet of data to be read from or written to a streaming driver pin.
old-location: stream\ksstream_header.htm
tech.root: stream
ms.assetid: c1057dcf-2988-460d-b006-f6cf16ec969e
ms.date: 04/23/2018
ms.keywords: "*PKSSTREAM_HEADER, KSSTREAM_HEADER, KSSTREAM_HEADER structure [Streaming Media Devices], PKSSTREAM_HEADER, PKSSTREAM_HEADER structure pointer [Streaming Media Devices], ks-struct_6f951af2-bee6-49ee-9df5-5291b5d00045.xml, ks/KSSTREAM_HEADER, ks/PKSSTREAM_HEADER, stream.ksstream_header"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSSTREAM_HEADER
product:
- Windows
targetos: Windows
req.typenames: KSSTREAM_HEADER, *PKSSTREAM_HEADER
---

# KSSTREAM_HEADER structure


## -description


The KSSTREAM_HEADER structure is a variable-length structure that describes a packet of data to be read from or written to a streaming driver pin.


## -struct-fields




### -field Size

Specifies the size, in bytes, of the structure. This should be at least <b>sizeof</b>(KSSTREAM_HEADER).


### -field TypeSpecificFlags

Specifies flags that are specific to a data format. The only flag currently supported for <i>TypeSpecificFlags</i> is KS_AM_UseNewCSSKey. This flag indicates that the hardware decoder should switch to the next queued CSS (Content Scramble System) decryption key, because the data sample that immediately follows the header is the first data sample to which a new title key applies.


### -field PresentationTime

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff567145">KSTIME</a> structure that specifies the presentation time for the related stream buffer in 100-nanosecond units. For more information, see the <b>Remarks</b> section.


### -field Duration

Specifies the duration of this stream segment in the same units as the presentation time (100-nanosecond units). Set to zero when not used.


### -field FrameExtent

Specifies the size of the entire frame. The region within the frame extent is available to the filter, and the resulting valid data size for the stream operation is reflected in the <b>DataUsed</b> member.


### -field DataUsed

For a write operation, this member specifies the number of bytes within the frame that are valid when submitting a frame to a lower-level driver. The headers are not modified on a write operation; however, the <b>Information</b> member of the IO_STATUS_BLOCK structure contains the total number of bytes actually written. For a read operation, this member is not used when submitting a frame to a lower-level driver and must be set to zero. On return, this member contains the number of bytes actually filled in this frame and the <b>Information</b> member of the IO_STATUS_BLOCK structure contains the size of the list of headers actually used. Note that if the minidriver specifies KSPIN_FLAG_GENERATE_MAPPINGS in <a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>, when a stream pointer is advanced past a frame, <b>DataUsed</b> is set to <b>Count</b> minus <b>Remaining</b> (members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567140">KSSTREAM_POINTER_OFFSET</a>). If the driver does not specify this flag, the minidriver is responsible for setting <b>DataUsed</b>.


### -field Data

Specifies the virtual address of the data buffer.


### -field OptionsFlags


  Specifies a variety of attributes of the data stream. The <b>OptionsFlags</b> member can have the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_DATADISCONTINUITY

</td>
<td>
Specifies that there has been a discontinuity in the data stream before the data that is contained in this packet. This implies that the filter might need to reset its internal state before processing the data. No actual data buffer need be attached.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_DURATIONVALID

</td>
<td>

          Specifies that the <b>Duration</b> member of this structure is valid.
        

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_ENDOFPHOTOSEQUENCE

</td>
<td>
Indicates that this frame represents the end of a photo sequence.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM

</td>
<td>
Indicates that this frame represents the end of the data stream.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_FLUSHONPAUSE

</td>
<td>
If the stream is paused, this buffer should be flushed. This flag is used, for example, by live data sources, where a pause renders the current data stale.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_FRAMEINFO

</td>
<td>
Indicates that there is a KS_FRAME_INFO structure following KSSTREAM_HEADER.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_LOOPEDDATA

</td>
<td>
This data buffer is the start of looped data. The driver should loop on this data until explicitly stopped.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_METADATA

</td>
<td>
Indicates that there is a KSSTREAM_METADATA_INFO that follows KS_FRAME_INFO after the KSSTREAM_HEADER. 
		  This flag is present only if KSPROPERTY_CAMERACONTROL_EXTENDED_METADATA is supported.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_PREROLL

</td>
<td>
The data in this buffer is used to prime the device state. This is a stream-specific option.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_SPLICEPOINT

</td>
<td>
The data stream is at a natural point for splicing. A client uses this, for example, when sending data that uses inter-frame compression, such as MPEG video, to indicate that it is safe to splice at this point.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_TIMEDISCONTINUITY

</td>
<td>
There is a discontinuity in the data stream after this packet. This flag can be used for positional oriented interfaces to indicate an end of stream data. No actual data buffer need be attached.

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_TIMEVALID

</td>
<td>

          Specifies that the <b>PresentationTime</b> member of this structure is valid. Indicates that this buffer has a valid timestamp associated with it.
        

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_TYPECHANGED

</td>
<td>

          Signifies that the data format for this stream has changed. If this flag is set, the <b>Data</b> member contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> structure that contains the new format. This flag is valid only for streams that have previously negotiated dynamic type changing. For a write operation, include the new data format in place of a media sample. If the media-specific extension size is modified, this header must be the last header in a list of headers for the given stream request. During a read request, any further I/O remains pending until the new format is retrieved through KSPROPERTY_CONNECTION_DATAFORMAT. For a write operation, the header must not be extended, and must be the only header in the write operation.
        

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_VRAM_DATA_TRANSFER

</td>
<td>

          Specifies that the stream header's <i>Data</i> member points to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff568783">VRAM_SURFACE_INFO</a>. The system-supplied KS proxy module sets this flag to indicate that it is <a href="https://msdn.microsoft.com/e3ab3a10-42af-488f-9b13-d2c6d5aac615">capturing directly to VRAM</a>.
        

</td>
</tr>
<tr>
<td>
KSSTREAM_HEADER_OPTIONSF_BUFFEREDTRANSFER

</td>
<td>

          Specifies that the <i>Data</i> member of KSSTREAM_HEADER contains a kernel-mode copy of the original buffer. Ksproxy sets this flag for small data transfers during WVDDM (Windows Vista Display Driver Model) capture. If this flag is not set, KS uses direct I/O into the <i>Data</i> buffer.
        

</td>
</tr>
</table>
 


### -field Reserved

Reserved for internal use.


## -remarks



This structure can be followed in memory by additional information specific to the type of data in the data packet.

The presentation time is typically in 100-nanosecond units; however, the standard format of this time is based on the data format. You can normalize presentation time by using as a scaling fractional the KSSTREAM_HEADER.PresentationTime.Numerator divided by the KSSTREAM_HEADER.PresentationTime.Denominator .

A conversion should use the numerator first, then the denominator, in order to reduce rounding errors. For example, an audio stream might present the current time as a byte offset in the data stream:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define BITS_PER_BYTE8
#define NANOSECONDS10000000
 
StreamHdr-&gt;PresentationTime.Numerator = BITS_PER_BYTE * NANOSECONDS;
StreamHdr-&gt;PresentationTime.Denominator = BitsPerSample * Channels * Frequency;
StreamHdr-&gt;PresentationTime.Time = ByteOffset;
StreamHdr-&gt;Duration = ByteLength;</pre>
</td>
</tr>
</table></span></div>
On an IOCTL_KS_READ_STREAM, portions of the stream header are filled in by the call. Each KSSTREAM_HEADER.DataUsed element contains the actual number of bytes read, which is less than or equal to each KSSTREAM_HEADER.FrameExtent. The pIrp-&gt;IoStatus.Information element contains the total size of the header data to return, which is at least one <b>sizeof</b>(KSSTREAM_HEADER).

On an IOCTL_KS_WRITE_STREAM, the member elements must be initialized, and each KSSTREAM_HEADER.DataUsed element contains the number of bytes to write. The actual number of total bytes written is returned in pIrp-&gt;IoStatus.Information. This is less than or equal to the total of all KSSTREAM_HEADER.DataUsed elements in the headers.

If you are using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560725">IKsReferenceClock</a> interface to obtain timestamps to place in the <b>PresentationTime</b> member of KSSTREAM_HEADER, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a> for more information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>
 

 

