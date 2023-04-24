---
UID: NS:ksmedia.tagKS_TVTUNER_CHANGE_INFO
title: KS_TVTUNER_CHANGE_INFO (ksmedia.h)
description: The KS_TVTUNER_CHANGE_INFO structure provides vertical blanking interval (VBI) codecs with information about the currently tuned channel.
tech.root: stream
ms.date: 03/15/2023
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
 - tagKS_TVTUNER_CHANGE_INFO
 - PKS_TVTUNER_CHANGE_INFO
 - KS_TVTUNER_CHANGE_INFO
---

## -description

The **KS_TVTUNER_CHANGE_INFO** structure provides vertical blanking interval (VBI) codecs with information about the currently tuned channel.

## -struct-fields

### -field dwFlags

Specifies flags indicating the status of the tuning operation. This member must be set to one of the following values that are defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KS_TVTUNER_CHANGE_BEGIN_TUNE | Indicates that a tuning operation has begun. VBI codecs should stop decoding at this time, because the video signal may become corrupted. |
| KS_TVTUNER_CHANGE_END_TUNE | Indicates completion of a tuning operation. VBI codecs should resume decoding. |

### -field dwCountryCode

Specifies the country code in use. This corresponds to the International Telecommunications Unit (ITU) long distance dialing code.

### -field dwAnalogVideoStandard

Specifies the current analog video standard. This member should be set to a value from the [KS_AnalogVideoStandard](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard) enumeration.

### -field dwChannel

Specifies the current channel number.

## -remarks

A packet containing a KS_TVTUNER_CHANGE_INFO structure normally originates at a TV tuner filter, and is propagated through any crossbars to an analog video decoder capture filter. The capture filter in turn must propagate this packet to downstream VBI codecs as part of a VBI media sample.

## -see-also

[KS_AnalogVideoStandard](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard)
