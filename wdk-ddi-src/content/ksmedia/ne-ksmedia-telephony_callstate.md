---
UID: NE:ksmedia.TELEPHONY_CALLSTATE
title: TELEPHONY_CALLSTATE (ksmedia.h)
description: The TELEPHONY_CALLSTATE enumeration defines constants that specify the state of a phone call.
old-location: audio\telephony_callstate.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["TELEPHONY_CALLSTATE enumeration"]
ms.keywords: TELEPHONY_CALLSTATE, TELEPHONY_CALLSTATE enumeration [Audio Devices], TELEPHONY_CALLSTATE_DISABLED, TELEPHONY_CALLSTATE_ENABLED, TELEPHONY_CALLSTATE_HOLD, TELEPHONY_CALLSTATE_PROVIDERTRANSITION, audio.telephony_callstate, ksmedia/TELEPHONY_CALLSTATE, ksmedia/TELEPHONY_CALLSTATE_DISABLED, ksmedia/TELEPHONY_CALLSTATE_ENABLED, ksmedia/TELEPHONY_CALLSTATE_HOLD, ksmedia/TELEPHONY_CALLSTATE_PROVIDERTRANSITION
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: None supported
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
req.typenames: TELEPHONY_CALLSTATE
f1_keywords:
 - TELEPHONY_CALLSTATE
 - ksmedia/TELEPHONY_CALLSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - TELEPHONY_CALLSTATE
---

# TELEPHONY_CALLSTATE enumeration


## -description

The <b>TELEPHONY_CALLSTATE</b> enumeration defines constants that specify the state of a phone call.

## -enum-fields

### -field TELEPHONY_CALLSTATE_DISABLED

Specifies that the phone call is disabled.

### -field TELEPHONY_CALLSTATE_ENABLED

Specifies that the phone call is enabled. This constant is set in a number of situations. For example, it will be set by the audio driver when the provider change operation is <b>TELEPHONY_PROVIDERCHANGEOP_END</b> and when <b>TELEPHONY_CALLCONTROLOP_ENABLE</b> is received.

### -field TELEPHONY_CALLSTATE_HOLD

Specifies that the phone call is on hold.

### -field TELEPHONY_CALLSTATE_PROVIDERTRANSITION

Specifies that the phone call is disabled. This constant is set by the audio driver when the provider change operation is <b>TELEPHONY_PROVIDERCHANGEOP_BEGIN</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_tagkstelephony_callinfo">KSTELEPHONY_CALLINFO</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-telephony_providerchangeop">TELEPHONY_PROVIDERCHANGEOP</a>

