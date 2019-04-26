---
UID: NE:ksmedia.__unnamed_enum_25
title: TELEPHONY_PROVIDERCHANGEOP (ksmedia.h)
description: The TELEPHONY_PROVIDERCHANGEOP enumeration defines constants that specify the requested provider change operation.
old-location: audio\telephony_providerchangeop.htm
tech.root: audio
ms.assetid: A229E8D5-2776-453B-B0F9-BC48E9D29A2F
ms.date: 05/08/2018
ms.keywords: TELEPHONY_PROVIDERCHANGEOP, TELEPHONY_PROVIDERCHANGEOP enumeration [Audio Devices], TELEPHONY_PROVIDERCHANGEOP_BEGIN, TELEPHONY_PROVIDERCHANGEOP_CANCEL, TELEPHONY_PROVIDERCHANGEOP_END, audio.telephony_providerchangeop, ksmedia/TELEPHONY_PROVIDERCHANGEOP, ksmedia/TELEPHONY_PROVIDERCHANGEOP_BEGIN, ksmedia/TELEPHONY_PROVIDERCHANGEOP_CANCEL, ksmedia/TELEPHONY_PROVIDERCHANGEOP_END
ms.topic: enum
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- TELEPHONY_PROVIDERCHANGEOP
product:
- Windows
targetos: Windows
req.typenames: TELEPHONY_PROVIDERCHANGEOP
---

# TELEPHONY_PROVIDERCHANGEOP enumeration


## -description


The <b>TELEPHONY_PROVIDERCHANGEOP</b> enumeration defines constants that specify the requested provider change operation.


## -enum-fields




### -field TELEPHONY_PROVIDERCHANGEOP_END

Specifies that the provider change operation has ended. The audio driver will update the call state to <b>TELEPHONY_CALLSTATE_ENABLED</b> in response to this value.


### -field TELEPHONY_PROVIDERCHANGEOP_BEGIN

Specifies that the provider change operation has begun. The audio driver will update the call state to <b>TELEPHONY_CALLSTATE_PROVIDERTRANSITION</b> in response to this value.


### -field TELEPHONY_PROVIDERCHANGEOP_CANCEL

Specifies that single-radio voice call continuity (SRVCC) is being canceled, and that the audio driver should revert back to the pre-SRVCC state. The audio driver will update the provider call state to TELEPHONY_CALLSTATE_ENABLED in response to this value.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt169876">KSPROPERTY_TELEPHONY_PROVIDERCHANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt169896">TELEPHONY_CALLSTATE</a>
 

 

