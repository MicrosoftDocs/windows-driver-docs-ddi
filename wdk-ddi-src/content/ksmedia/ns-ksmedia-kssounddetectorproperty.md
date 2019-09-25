---
UID: NS:ksmedia.__unnamed_struct_39
title: KSSOUNDDETECTORPROPERTY (ksmedia.h)
description: The KSSOUNDDETECTORPROPERTY structure specifies a node and a property of that node.
old-location: audio\KSSOUNDDETECTORPROPERTY.htm
tech.root: audio
ms.assetid: bbcf7597-217a-499b-b0f2-deef1e85becb
ms.date: 09/25/2019
ms.keywords: "*PKSSOUNDDETECTORPROPERTY, KSSOUNDDETECTORPROPERTY, KSSOUNDDETECTORPROPERTYstructure [Audio Devices], PKSSOUNDDETECTORPROPERTY, PKSSOUNDDETECTORPROPERTYstructure pointer [Audio Devices], audio.KSSOUNDDETECTORPROPERTY, ksmedia/KSSOUNDDETECTORPROPERTY, ksmedia/PKSSOUNDDETECTORPROPERTY"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSSOUNDDETECTORPROPERTY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSSOUNDDETECTORPROPERTY
product:
- Windows
targetos: Windows
req.typenames: KSSOUNDDETECTORPROPERTY, *PKSSOUNDDETECTORPROPERTY
---

# KSSOUNDDETECTORPROPERTY structure

## -description

The KSSOUNDDETECTORPROPERTY structure specifies a node and a property of that node.

## -struct-fields

### -field Property

Specifies the property to get or set. This member is a structure of type <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.

### -field EventId

Specifies the event ID.

## -remarks

This structure is identical to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksp_node">KSP_NODE</a>.

See the discussion of the KSSOUNDDETECTORPROPERTY structure in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-property-requests">Audio Property Requests</a>.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>


