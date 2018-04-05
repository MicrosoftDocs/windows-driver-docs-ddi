---
UID: NS:ksmedia._tagKSTELEPHONY_PROVIDERCHANGE
title: "_tagKSTELEPHONY_PROVIDERCHANGE"
author: windows-driver-content
description: The KSTELEPHONY_PROVIDERCHANGE structure specifies the phone call type and provider change operation to use for the KSPROPERTY_TELEPHONY_PROVIDERCHANGE property.
old-location: audio\kstelephony_providerchange.htm
old-project: audio
ms.assetid: 07928837-321C-4501-BDFF-4611BF6912F6
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSTELEPHONY_PROVIDERCHANGE, KSTELEPHONY_PROVIDERCHANGE, KSTELEPHONY_PROVIDERCHANGE structure [Audio Devices], PKSTELEPHONY_PROVIDERCHANGE, PKSTELEPHONY_PROVIDERCHANGE structure pointer [Audio Devices], _tagKSTELEPHONY_PROVIDERCHANGE, audio.kstelephony_providerchange, ksmedia/KSTELEPHONY_PROVIDERCHANGE, ksmedia/PKSTELEPHONY_PROVIDERCHANGE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSTELEPHONY_PROVIDERCHANGE
product:
- Windows
targetos: Windows
req.typenames: KSTELEPHONY_PROVIDERCHANGE, *PKSTELEPHONY_PROVIDERCHANGE
---

# _tagKSTELEPHONY_PROVIDERCHANGE structure


## -description


The <b>KSTELEPHONY_PROVIDERCHANGE</b> structure specifies the phone call type and provider change operation to use for the <a href="https://msdn.microsoft.com/library/windows/hardware/mt169876">KSPROPERTY_TELEPHONY_PROVIDERCHANGE</a> property.


## -struct-fields




### -field CallType

Specifies the type of phone call (circuit-switched, LTE packet-switched, or WLAN packet-switched).


### -field ProviderChangeOp

Specifies the change operation requested by the provider (begin, end, or cancel).


## -remarks



The audio stack uses the KSTELEPHONY_PROVIDERCHANGE property to indicate the start and the end of SRVCC to the audio driver. This property communicates the call type (LTE packet-switched, WLAN packet-switched, or circuit-switched) and the provider change operation (begin, end, or cancel) to driver. The call type is ignored when the provider operation is for ending the SRVCC. 

When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_BEGIN, the driver updates that provider’s call state to TELEPHONY_CALLSTATE_PROVIDERTRANSITION. When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_END, the driver updates that provider’s call state to TELEPHONY_CALLSTATE_ENABLED. During SRVCC, the driver must continue to use the associated KSNODETYPE_TELEPHONY_BIDI endpoint, and it does not change the jack states of this endpoint. When the provider change operation is TELEPHONY_PROVIDERCHANGEOP_CANCEL, SRVCC is being canceled, and the driver should revert back to a pre-SRVCC call.



