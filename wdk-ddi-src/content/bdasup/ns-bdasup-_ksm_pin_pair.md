---
UID: NS:bdasup._KSM_PIN_PAIR
title: _KSM_PIN_PAIR (bdasup.h)
description: The KSM_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.
old-location: stream\ksm_pin_pair.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSM_PIN_PAIR structure"]
ms.keywords: "*PKSM_PIN_PAIR, KSM_PIN_PAIR, KSM_PIN_PAIR structure [Streaming Media Devices], PKSM_PIN_PAIR, PKSM_PIN_PAIR structure pointer [Streaming Media Devices], _KSM_PIN_PAIR, bdaref_4d2071d5-ba64-4026-95a9-0763dc2f13cf.xml, bdasup/KSM_PIN_PAIR, bdasup/PKSM_PIN_PAIR, stream.ksm_pin_pair"
req.header: bdasup.h
req.include-header: Bdasup.h
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
req.typenames: KSM_PIN_PAIR, *PKSM_PIN_PAIR
f1_keywords:
 - _KSM_PIN_PAIR
 - bdasup/_KSM_PIN_PAIR
 - PKSM_PIN_PAIR
 - bdasup/PKSM_PIN_PAIR
 - KSM_PIN_PAIR
 - bdasup/KSM_PIN_PAIR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bdasup.h
api_name:
 - _KSM_PIN_PAIR
 - PKSM_PIN_PAIR
 - KSM_PIN_PAIR
---

# _KSM_PIN_PAIR structure


## -description

The KSM_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.

## -struct-fields

### -field Method

KSMETHOD structure that describes a method and request type of a method request.

### -field InputPinId

Identifier of an input pin of the filter.

### -field OutputPinId

Identifier of an output pin of the filter.

### -field Reserved

Reserved.

## -see-also

<a href="/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_pin_pairing">BDA_PIN_PAIRING</a>



<a href="/previous-versions/ff563398(v=vs.85)">KSMETHOD</a>

