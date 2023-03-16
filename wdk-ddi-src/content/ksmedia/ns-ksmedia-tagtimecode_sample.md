---
UID: NS:ksmedia.tagTIMECODE_SAMPLE
title: TIMECODE_SAMPLE (ksmedia.h)
description: The TIMECODE_SAMPLE structure describes a complete timecode.
tech.root: stream
ms.date: 03/15/2023
keywords: ["tagTIMECODE_SAMPLE structure"]
ms.keywords: "*PTIMECODE_SAMPLE, TIMECODE_SAMPLE, TIMECODE_SAMPLE structure [Streaming Media Devices], ksmedia/TIMECODE_SAMPLE, stream.timecode_sample, tagTIMECODE_SAMPLE, vidcapstruct_518cf1af-a1e2-43a6-b97f-115c4fe8cb6d.xml"
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
req.typenames: TIMECODE_SAMPLE
f1_keywords:
 - tagTIMECODE_SAMPLE
 - ksmedia/tagTIMECODE_SAMPLE
 - TIMECODE_SAMPLE
 - ksmedia/TIMECODE_SAMPLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagTIMECODE_SAMPLE
 - TIMECODE_SAMPLE
---

## -description

The TIMECODE_SAMPLE structure describes a complete timecode.

## -struct-fields

### -field qwTick

Specifies a reference time, in 100-nanosecond units.

### -field timecode

Specifies the [**TIMECODE**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_timecode) structure.

### -field dwUser

Specifies packed SMPTE user-bits.

### -field dwFlags

Specifies any optional timecode flag masks.

| Flag | Meaning |
|---|---|
| AM_TIMECODE_FLAG_FCM | Frame-code mode; 0 = nondrop; 1 = drop. |
| AM_TIMECODE_FLAG_CF | Color-frame flag. |
| AM_TIMECODE_FLAG_FIELD | Field flag. |
| AM_TIMECODE_FLAG_DF | Drop-frame flag (from flags in actual timecode on external media). |
| AM_TIMECODE_COLORFRAME | Specifies frame, in color sequence. |
| AM_TIMECODE_COLORSEQUENCE | Duration, in frames, of complete sequence. |
| AM_TIMECODE_FILMSEQUENCE_TYPE | One of the FILM_SEQUENCE\_*XXX* tokens. |
| ED_DEVCAP_TIMECODE_READ | Read SMPTE timecode; applies to DV camcorders. |
| ED_DEVCAP_ATN_READ | Read the absolute track number (ATN); applies to DV camcorders. |
| ED_DEVCAP_RTC_READ | Read the relative time counter (RTC); applies to MPEG camcorders. |

## -remarks

Any ED_Xxx tokens are defined in *xprtdefs.h* in the DirectX SDK.

The upper 16 bits in **dwFlags** are reserved for future use and must be set to zero.

## -see-also

[**TIMECODE**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_timecode)
