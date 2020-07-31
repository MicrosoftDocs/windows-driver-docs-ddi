---
UID: NS:ks.__unnamed_struct_47
title: KSSTREAM_HEADER (ks.h)
description: The KSSTREAM_HEADER structure is a variable-length structure that describes a packet of data to be read from or written to a streaming driver pin.
old-location: stream\ksstream_header.htm
tech.root: stream
ms.assetid: c1057dcf-2988-460d-b006-f6cf16ec969e
ms.date: 04/23/2018
keywords: ["KSSTREAM_HEADER structure"]
ms.keywords: "*PKSSTREAM_HEADER, KSSTREAM_HEADER, KSSTREAM_HEADER structure [Streaming Media Devices], PKSSTREAM_HEADER, PKSSTREAM_HEADER structure pointer [Streaming Media Devices], ks-struct_6f951af2-bee6-49ee-9df5-5291b5d00045.xml, ks/KSSTREAM_HEADER, ks/PKSSTREAM_HEADER, stream.ksstream_header"
f1_keywords:
 - "ks/KSSTREAM_HEADER"
 - "KSSTREAM_HEADER"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSSTREAM_HEADER
targetos: Windows
req.typenames: KSSTREAM_HEADER, *PKSSTREAM_HEADER
ms.custom: 19H1
---

# KSSTREAM_HEADER structure

## -description

The KSSTREAM_HEADER structure is a variable-length structure that describes a packet of data to be read from or written to a streaming driver pin.

## -struct-fields

### -field Size

Specifies the size, in bytes, of the structure. This should be at least **sizeof**(KSSTREAM_HEADER).

### -field TypeSpecificFlags

Specifies flags that are specific to a data format. The only flag currently supported for *TypeSpecificFlags* is KS_AM_UseNewCSSKey. This flag indicates that the hardware decoder should switch to the next queued CSS (Content Scramble System) decryption key, because the data sample that immediately follows the header is the first data sample to which a new title key applies.

### -field PresentationTime

A [KSTIME](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kstime) structure that specifies the presentation time for the related stream buffer in 100-nanosecond units. For more information, see the **Remarks** section.

### -field Duration

Specifies the duration of this stream segment in the same units as the presentation time (100-nanosecond units). Set to zero when not used.

### -field FrameExtent

Specifies the size of the entire frame. The region within the frame extent is available to the filter, and the resulting valid data size for the stream operation is reflected in the **DataUsed** member.

### -field DataUsed

For a write operation, this member specifies the number of bytes within the frame that are valid when submitting a frame to a lower-level driver. The headers are not modified on a write operation; however, the **Information** member of the IO_STATUS_BLOCK structure contains the total number of bytes actually written. For a read operation, this member is not used when submitting a frame to a lower-level driver and must be set to zero. On return, this member contains the number of bytes actually filled in this frame and the **Information** member of the IO_STATUS_BLOCK structure contains the size of the list of headers actually used. Note that if the minidriver specifies KSPIN_FLAG_GENERATE_MAPPINGS in [KSPIN_DESCRIPTOR_EX](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex), when a stream pointer is advanced past a frame, **DataUsed** is set to **Count** minus **Remaining** (members of [KSSTREAM_POINTER_OFFSET](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer_offset)). If the driver does not specify this flag, the minidriver is responsible for setting **DataUsed**.

### -field Data

Specifies the virtual address of the data buffer.

### -field OptionsFlags

Specifies a variety of attributes of the data stream. The **OptionsFlags** member can have the values listed in the following table.

| Value | Description |
| --- | --- |
| KSSTREAM_HEADER_OPTIONSF_DATADISCONTINUITY | Specifies that there has been a discontinuity in the data stream before the data that is contained in this packet. This implies that the filter might need to reset its internal state before processing the data. No actual data buffer need be attached. |
| KSSTREAM_HEADER_OPTIONSF_DURATIONVALID | Specifies that the **Duration** member of this structure is valid. |
| KSSTREAM_HEADER_OPTIONSF_ENDOFPHOTOSEQUENCE | Indicates that this frame represents the end of a photo sequence. |
| KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM | Indicates that this frame represents the end of the data stream. |
| KSSTREAM_HEADER_OPTIONSF_FLUSHONPAUSE | If the stream is paused, this buffer should be flushed. This flag is used, for example, by live data sources, where a pause renders the current data stale. |
| KSSTREAM_HEADER_OPTIONSF_FRAMEINFO | Indicates that there is a KS_FRAME_INFO structure following KSSTREAM_HEADER. |
| KSSTREAM_HEADER_OPTIONSF_LOOPEDDATA | This data buffer is the start of looped data. The driver should loop on this data until explicitly stopped. |
| KSSTREAM_HEADER_OPTIONSF_METADATA | Indicates that there is a KSSTREAM_METADATA_INFO that follows KS_FRAME_INFO after the KSSTREAM_HEADER. This flag is present only if KSPROPERTY_CAMERACONTROL_EXTENDED_METADATA is supported. |
| KSSTREAM_HEADER_OPTIONSF_PREROLL | The data in this buffer is used to prime the device state. This is a stream-specific option. |
| KSSTREAM_HEADER_OPTIONSF_SPLICEPOINT | The data stream is at a natural point for splicing. A client uses this, for example, when sending data that uses inter-frame compression, such as MPEG video, to indicate that it is safe to splice at this point. |
| KSSTREAM_HEADER_OPTIONSF_TIMEDISCONTINUITY | There is a discontinuity in the data stream after this packet. This flag can be used for positional oriented interfaces to indicate an end of stream data. No actual data buffer need be attached. |
| KSSTREAM_HEADER_OPTIONSF_TIMEVALID | Specifies that the **PresentationTime** member of this structure is valid. Indicates that this buffer has a valid timestamp associated with it. |
| KSSTREAM_HEADER_OPTIONSF_TYPECHANGED | Signifies that the data format for this stream has changed. If this flag is set, the **Data** member contains a [KSDATAFORMAT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat) structure that contains the new format. This flag is valid only for streams that have previously negotiated dynamic type changing. For a write operation, include the new data format in place of a media sample. If the media-specific extension size is modified, this header must be the last header in a list of headers for the given stream request. During a read request, any further I/O remains pending until the new format is retrieved through KSPROPERTY_CONNECTION_DATAFORMAT. For a write operation, the header must not be extended, and must be the only header in the write operation. |
| KSSTREAM_HEADER_OPTIONSF_VRAM_DATA_TRANSFER | Specifies that the stream header's *Data* member points to a structure of type [VRAM_SURFACE_INFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-vram_surface_info). The system-supplied KS proxy module sets this flag to indicate that it is [capturing directly to VRAM](https://docs.microsoft.com/windows-hardware/drivers/stream/vram-capture-properties). |
| KSSTREAM_HEADER_OPTIONSF_BUFFEREDTRANSFER | Specifies that the *Data* member of KSSTREAM_HEADER contains a kernel-mode copy of the original buffer. Ksproxy sets this flag for small data transfers during WVDDM (Windows Vista Display Driver Model) capture. If this flag is not set, KS uses direct I/O into the *Data* buffer. |

### -field Reserved

Reserved for internal use.

## -remarks

This structure can be followed in memory by additional information specific to the type of data in the data packet.

The presentation time is typically in 100-nanosecond units; however, the standard format of this time is based on the data format. You can normalize presentation time by using as a scaling fractional the KSSTREAM_HEADER.PresentationTime.Numerator divided by the KSSTREAM_HEADER.PresentationTime.Denominator .

A conversion should use the numerator first, then the denominator, in order to reduce rounding errors. For example, an audio stream might present the current time as a byte offset in the data stream:

```cpp
#define BITS_PER_BYTE8
#define NANOSECONDS10000000

StreamHdr->PresentationTime.Numerator = BITS_PER_BYTE * NANOSECONDS;
StreamHdr->PresentationTime.Denominator = BitsPerSample * Channels * Frequency;
StreamHdr->PresentationTime.Time = ByteOffset;
StreamHdr->Duration = ByteLength;
```

On an IOCTL_KS_READ_STREAM, portions of the stream header are filled in by the call. Each KSSTREAM_HEADER.DataUsed element contains the actual number of bytes read, which is less than or equal to each KSSTREAM_HEADER.FrameExtent. The pIrp->IoStatus.Information element contains the total size of the header data to return, which is at least one **sizeof**(KSSTREAM_HEADER).

On an IOCTL_KS_WRITE_STREAM, the member elements must be initialized, and each KSSTREAM_HEADER.DataUsed element contains the number of bytes to write. The actual number of total bytes written is returned in pIrp->IoStatus.Information. This is less than or equal to the total of all KSSTREAM_HEADER.DataUsed elements in the headers.

If you are using the [IKsReferenceClock](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nn-ks-iksreferenceclock) interface to obtain timestamps to place in the **PresentationTime** member of KSSTREAM_HEADER, see [AVStream Clocks](https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-clocks) for more information.

## -see-also

[KSDATAFORMAT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat)
