---
UID: NS:ksmedia.__unnamed_struct_37
title: KSRTAUDIO_PACKETVREGISTER (ksmedia.h)
description: The KSRTAUDIO_PACKETVREGISTER structure contains information about the packet virtual register pointers.
ms.assetid: 42c9a5a1-0d6c-447b-918e-70ab47c4720d
ms.date: 09/28/2018
keywords: ["KSRTAUDIO_PACKETVREGISTER structure"]
ms.keywords: KSRTAUDIO_PACKETVREGISTER, KSRTAUDIO_PACKETVREGISTER, *PKSRTAUDIO_PACKETVREGISTER,
req.header: ksmedia.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: KSRTAUDIO_PACKETVREGISTER, *PKSRTAUDIO_PACKETVREGISTER
targetos: Windows
ms.custom: RS5
f1_keywords:
 - PKSRTAUDIO_PACKETVREGISTER
 - ksmedia/PKSRTAUDIO_PACKETVREGISTER
 - KSRTAUDIO_PACKETVREGISTER
 - ksmedia/KSRTAUDIO_PACKETVREGISTER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSRTAUDIO_PACKETVREGISTER
---

# KSRTAUDIO_PACKETVREGISTER structure


## -description

The **KSRTAUDIO_PACKETVREGISTER** structure contains information about the packet virtual register pointers.

## -struct-fields

### -field CompletedPacketCount

A PULONG64 pointer to the completed packet count buffer.

### -field CompletedPacketQPC

A PULONG64 pointer to the query performance counter (QPC) value.

### -field CompletedPacketHash

 
A PULONG64 pointer to the packet hash value that is a combination of the two low-order DWORDs for count and QPC.

## -remarks

## -see-also

[KSPROPSETID_RTAudio](/windows-hardware/drivers/audio/kspropsetid-rtaudio)