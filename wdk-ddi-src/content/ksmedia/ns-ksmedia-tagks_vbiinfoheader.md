---
UID: NS:ksmedia.tagKS_VBIINFOHEADER
title: tagKS_VBIINFOHEADER (ksmedia.h)
description: The KS_VBIINFOHEADER structure describes raw vertical blanking interval (VBI) streams.
old-location: stream\ks_vbiinfoheader.htm
tech.root: stream
ms.assetid: 4424be3a-6e73-449c-b5fb-5cbc1109490d
ms.date: 04/23/2018
keywords: ["tagKS_VBIINFOHEADER structure"]
ms.keywords: "*PKS_VBIINFOHEADER, KS_VBIINFOHEADER, KS_VBIINFOHEADER structure [Streaming Media Devices], PKS_VBIINFOHEADER, PKS_VBIINFOHEADER structure pointer [Streaming Media Devices], ksmedia/KS_VBIINFOHEADER, ksmedia/PKS_VBIINFOHEADER, stream.ks_vbiinfoheader, tagKS_VBIINFOHEADER, vidcapstruct_2a637c59-2852-4b59-9d92-f51c9892df85.xml"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
targetos: Windows
req.typenames: KS_VBIINFOHEADER, *PKS_VBIINFOHEADER
f1_keywords:
 - tagKS_VBIINFOHEADER
 - ksmedia/tagKS_VBIINFOHEADER
 - PKS_VBIINFOHEADER
 - ksmedia/PKS_VBIINFOHEADER
 - KS_VBIINFOHEADER
 - ksmedia/KS_VBIINFOHEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_VBIINFOHEADER
---

# tagKS_VBIINFOHEADER structure


## -description

The KS_VBIINFOHEADER structure describes raw vertical blanking interval (VBI) streams.

## -struct-fields

### -field StartLine

Specifies the line number of the first digitized VBI line.

### -field EndLine

Specifies the line number of the last digitized VBI line.

### -field SamplingFrequency

Specifies the sampling frequency in hertz (Hz).

### -field MinLineStartTime

Specifies the shortest possible interval from the leading edge of H-sync in 10-nanosecond units (that is, in hundredths of microseconds).

### -field MaxLineStartTime

Specifies the longest possible interval from the leading edge of H-sync in 10-nanosecond units (that is, in hundredths of microseconds).

### -field ActualLineStartTime

Specifies the actual starting point of VBI digitization from the leading edge of H-sync in 10-nanosecond units (that is, in hundredths of microseconds).

### -field ActualLineEndTime

Specifies the actual ending point for VBI digitization from the leading edge of H-sync in 10-nanosecond units (that is, in hundredths of microseconds).

### -field VideoStandard

Specifies one or more (logically ORed) values from the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a> enumeration.

### -field SamplesPerLine

Specifies the number of samples digitized per video line.

### -field StrideInBytes

Specifies the stride in bytes between the first sample on a given line and the first sample on the next line. This value can be larger than <b>SamplesPerLine</b>.

### -field BufferSize

Specifies the size in bytes of the buffer to store the entire digitized VBI signal.

## -remarks

VBI streams are usually converted to NABTS, CC, and WST streams by downstream filters.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a>