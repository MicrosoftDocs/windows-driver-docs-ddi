---
UID: NS:bdasup._KSM_PIN_PAIR
title: _KSM_PIN_PAIR (bdasup.h)
description: The KSM_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.
old-location: stream\ksm_pin_pair.htm
tech.root: stream
ms.assetid: a38e1215-4689-4b75-9a32-4d6570694b77
ms.date: 04/23/2018
ms.keywords: "*PKSM_PIN_PAIR, KSM_PIN_PAIR, KSM_PIN_PAIR structure [Streaming Media Devices], PKSM_PIN_PAIR, PKSM_PIN_PAIR structure pointer [Streaming Media Devices], _KSM_PIN_PAIR, bdaref_4d2071d5-ba64-4026-95a9-0763dc2f13cf.xml, bdasup/KSM_PIN_PAIR, bdasup/PKSM_PIN_PAIR, stream.ksm_pin_pair"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bdasup.h
api_name:
- KSM_PIN_PAIR
product:
- Windows
targetos: Windows
req.typenames: KSM_PIN_PAIR, *PKSM_PIN_PAIR
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556544">BDA_PIN_PAIRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>
 

 

