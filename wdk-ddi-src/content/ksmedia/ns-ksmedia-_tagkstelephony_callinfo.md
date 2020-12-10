---
UID: NS:ksmedia._tagKSTELEPHONY_CALLINFO
title: _tagKSTELEPHONY_CALLINFO (ksmedia.h)
description: The KSTELEPHONY_CALLINFO structure specifies the type and state of a phone call for the KSPROPERTY_TELEPHONY_CALLINFO property.
old-location: audio\kstelephony_callinfo.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["tagKSTELEPHONY_CALLINFO structure"]
ms.keywords: "*PKSTELEPHONY_CALLINFO, KSTELEPHONY_CALLINFO, KSTELEPHONY_CALLINFO structure [Audio Devices], PKSTELEPHONY_CALLINFO, PKSTELEPHONY_CALLINFO structure pointer [Audio Devices], _tagKSTELEPHONY_CALLINFO, audio.kstelephony_callinfo, ksmedia/KSTELEPHONY_CALLINFO, ksmedia/PKSTELEPHONY_CALLINFO"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: Windows Server 2016
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
req.typenames: KSTELEPHONY_CALLINFO, *PKSTELEPHONY_CALLINFO
f1_keywords:
 - _tagKSTELEPHONY_CALLINFO
 - ksmedia/_tagKSTELEPHONY_CALLINFO
 - PKSTELEPHONY_CALLINFO
 - ksmedia/PKSTELEPHONY_CALLINFO
 - KSTELEPHONY_CALLINFO
 - ksmedia/KSTELEPHONY_CALLINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSTELEPHONY_CALLINFO
---

# _tagKSTELEPHONY_CALLINFO structure


## -description

The <b>KSTELEPHONY_CALLINFO</b> structure specifies the type and state of a phone call for the <a href="/windows-hardware/drivers/audio/ksproperty-telephony-callinfo">KSPROPERTY_TELEPHONY_CALLINFO</a> property.

## -struct-fields

### -field CallType

Specifies the type of phone call (circuit-switched, LTE packet-switched, or WLAN packet-switched).

### -field CallState

Specifies the state of the phone call.
