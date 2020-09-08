---
UID: NS:ksmedia.tagKS_TVTUNER_CHANGE_INFO
title: tagKS_TVTUNER_CHANGE_INFO (ksmedia.h)
description: The KS_TVTUNER_CHANGE_INFO structure provides vertical blanking interval (VBI) codecs with information about the currently tuned channel.
old-location: stream\ks_tvtuner_change_info.htm
tech.root: stream
ms.assetid: 7bb04fbb-2894-4148-88c2-fbbebb000ec9
ms.date: 04/23/2018
keywords: ["tagKS_TVTUNER_CHANGE_INFO structure"]
ms.keywords: "*PKS_TVTUNER_CHANGE_INFO, KS_TVTUNER_CHANGE_INFO, KS_TVTUNER_CHANGE_INFO structure [Streaming Media Devices], PKS_TVTUNER_CHANGE_INFO, PKS_TVTUNER_CHANGE_INFO structure pointer [Streaming Media Devices], ksmedia/KS_TVTUNER_CHANGE_INFO, ksmedia/PKS_TVTUNER_CHANGE_INFO, stream.ks_tvtuner_change_info, tagKS_TVTUNER_CHANGE_INFO, vidcapstruct_225fdabf-bdaf-49df-a2e3-ace62a0a17e2.xml"
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
req.typenames: KS_TVTUNER_CHANGE_INFO, *PKS_TVTUNER_CHANGE_INFO
f1_keywords:
 - tagKS_TVTUNER_CHANGE_INFO
 - ksmedia/tagKS_TVTUNER_CHANGE_INFO
 - PKS_TVTUNER_CHANGE_INFO
 - ksmedia/PKS_TVTUNER_CHANGE_INFO
 - KS_TVTUNER_CHANGE_INFO
 - ksmedia/KS_TVTUNER_CHANGE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_TVTUNER_CHANGE_INFO
---

# tagKS_TVTUNER_CHANGE_INFO structure


## -description

The KS_TVTUNER_CHANGE_INFO structure provides vertical blanking interval (VBI) codecs with information about the currently tuned channel.

## -struct-fields

### -field dwFlags

Specifies flags indicating the status of the tuning operation. This member must be set to one of the following values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_TVTUNER_CHANGE_BEGIN_TUNE

</td>
<td>
Indicates that a tuning operation has begun. VBI codecs should stop decoding at this time, because the video signal may become corrupted.

</td>
</tr>
<tr>
<td>
KS_TVTUNER_CHANGE_END_TUNE

</td>
<td>
Indicates completion of a tuning operation. VBI codecs should resume decoding.

</td>
</tr>
</table>

### -field dwCountryCode

Specifies the country code in use. This corresponds to the International Telecommunications Unit (ITU) long distance dialing code.

### -field dwAnalogVideoStandard

Specifies the current analog video standard. This member should be set to a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a> enumeration.

### -field dwChannel

Specifies the current channel number.

## -remarks

A packet containing a KS_TVTUNER_CHANGE_INFO structure normally originates at a TV tuner filter, and is propagated through any crossbars to an analog video decoder capture filter. The capture filter in turn must propagate this packet to downstream VBI codecs as part of a VBI media sample.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a>

