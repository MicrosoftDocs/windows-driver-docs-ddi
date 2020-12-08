---
UID: NS:ksmedia.__unnamed_struct_39
title: KSSOUNDDETECTORPROPERTY (ksmedia.h)
description: The KSSOUNDDETECTORPROPERTY structure specifies a node and an Event ID.
old-location: audio\KSSOUNDDETECTORPROPERTY.htm
tech.root: audio
ms.date: 09/25/2019
keywords: ["KSSOUNDDETECTORPROPERTY structure"]
ms.keywords: "*PKSSOUNDDETECTORPROPERTY, KSSOUNDDETECTORPROPERTY, KSSOUNDDETECTORPROPERTYstructure [Audio Devices], PKSSOUNDDETECTORPROPERTY, PKSSOUNDDETECTORPROPERTYstructure pointer [Audio Devices], audio.KSSOUNDDETECTORPROPERTY, ksmedia/KSSOUNDDETECTORPROPERTY, ksmedia/PKSSOUNDDETECTORPROPERTY"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1903
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
req.typenames: KSSOUNDDETECTORPROPERTY, *PKSSOUNDDETECTORPROPERTY
f1_keywords:
 - PKSSOUNDDETECTORPROPERTY
 - ksmedia/PKSSOUNDDETECTORPROPERTY
 - KSSOUNDDETECTORPROPERTY
 - ksmedia/KSSOUNDDETECTORPROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSSOUNDDETECTORPROPERTY
---

# KSSOUNDDETECTORPROPERTY structure


## -description

The KSSOUNDDETECTORPROPERTY structure specifies a node and an Event ID. All sound detector property calls into the driver are made using the KSSOUNDDETECTORPROPERTY structure.

## -struct-fields

### -field Property

Specifies the property to get or set. This member is a structure of type <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.

### -field EventId

Specifies the event ID GUID.

## -remarks

The EventId is used to identify the different voice assistant/agents such as Cortana. By including the event id with all of the KSPROPERTY_SOUNDDETECTOR_* properties, each agent can be controlled separately, for example like arming "Cortana" without arming "Contoso".

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>

<a href="/windows-hardware/drivers/audio/voice-activation-mva">Mulitple Voice Assistant</a>
