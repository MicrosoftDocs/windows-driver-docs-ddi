---
UID: NS:ksmedia.MEDIUM_INFO
title: MEDIUM_INFO (ksmedia.h)
description: The MEDIUM_INFO structure describes the media loaded into an external device.
tech.root: stream
ms.date: 03/15/2023
keywords: ["MEDIUM_INFO structure"]
ms.keywords: "*PMEDIUM_INFO, MEDIUM_INFO, MEDIUM_INFO structure [Streaming Media Devices], PMEDIUM_INFO, PMEDIUM_INFO structure pointer [Streaming Media Devices], ksmedia/MEDIUM_INFO, ksmedia/PMEDIUM_INFO, stream.medium_info, vidcapstruct_f83c29e1-51a8-4784-a785-4e5dc9956634.xml"
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
req.typenames: MEDIUM_INFO, *PMEDIUM_INFO
f1_keywords:
 - PMEDIUM_INFO
 - ksmedia/PMEDIUM_INFO
 - MEDIUM_INFO
 - ksmedia/MEDIUM_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PMEDIUM_INFO
 - MEDIUM_INFO
---

## -description

The **MEDIUM_INFO** structure describes the media loaded into an external device.

## -struct-fields

### -field MediaPresent

Specifies if media is present in the external device. **TRUE** if media is loaded, **FALSE** otherwise.

### -field MediaType

Indicates the type of the media loaded in an external device.

| Flag | Meaning |
|---|---|
| ED_MEDIA_DVC | Digital video cassette. For example MiniDV |
| ED_MEDIA_VHS | VHS cassette |
| ED_MEDIA_HI8 | Hi-8 cassette |

### -field RecordInhibit

Specifies if recording is inhibited on the media. **TRUE** if recording onto the media is inhibited, **FALSE** otherwise.

## -remarks

Any ED_Xxx tokens are defined in *xprtdefs.h* in the Microsoft DirectX SDK.
