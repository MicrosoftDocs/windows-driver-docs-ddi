---
UID: NS:bdamedia._KSM_BDA_PIN_PAIR
title: _KSM_BDA_PIN_PAIR (bdamedia.h)
description: The KSM_BDA_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.
old-location: stream\ksm_bda_pin_pair.htm
tech.root: stream
ms.assetid: 310a3faf-de71-4965-9511-cb8feca7087c
ms.date: 04/23/2018
keywords: ["_KSM_BDA_PIN_PAIR structure"]
ms.keywords: "*PKSM_BDA_PIN_PAIR, KSM_BDA_PIN_PAIR, KSM_BDA_PIN_PAIR structure [Streaming Media Devices], PKSM_BDA_PIN_PAIR, PKSM_BDA_PIN_PAIR structure pointer [Streaming Media Devices], _KSM_BDA_PIN_PAIR, bdamedia/KSM_BDA_PIN_PAIR, bdamedia/PKSM_BDA_PIN_PAIR, bdaref_c171cffc-e7e6-432b-98ae-f198fdc20079.xml, stream.ksm_bda_pin_pair"
f1_keywords:
 - "bdamedia/KSM_BDA_PIN_PAIR"
 - "KSM_BDA_PIN_PAIR"
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
- bdamedia.h
api_name:
- KSM_BDA_PIN_PAIR
targetos: Windows
req.typenames: KSM_BDA_PIN_PAIR, *PKSM_BDA_PIN_PAIR
---

# _KSM_BDA_PIN_PAIR structure


## -description


The KSM_BDA_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins. 


## -struct-fields




### -field Method

KSMETHOD structure that describes a method and request type of a method request.


### -field InputPinId

Member of the union in KSM_BDA_PIN_PAIR that contains the identifier (ID) of an input pin of the filter.


### -field InputPinType

Member of the union in KSM_BDA_PIN_PAIR that contains the value that specifies the input pin type.


### -field OutputPinId

Member of the union in KSM_BDA_PIN_PAIR that contains the identifier (ID) of an output pin of the filter.


### -field OutputPinType

Member of the union in KSM_BDA_PIN_PAIR that contains the value that specifies the output pin type.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bdasup/ns-bdasup-_bda_pin_pairing">BDA_PIN_PAIRING</a>



<a href="https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)">KSMETHOD</a>
 

 

