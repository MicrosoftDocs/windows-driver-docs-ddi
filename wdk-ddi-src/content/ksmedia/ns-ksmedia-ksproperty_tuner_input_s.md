---
UID: NS:ksmedia.KSPROPERTY_TUNER_INPUT_S
title: KSPROPERTY_TUNER_INPUT_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_INPUT_S structure describes the input connection index of a tuner device for devices that support multiple inputs.
old-location: stream\ksproperty_tuner_input_s.htm
old-project: stream
ms.assetid: 02873563-7448-4406-a8ab-599569abbf7e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_TUNER_INPUT_S, KSPROPERTY_TUNER_INPUT_S, KSPROPERTY_TUNER_INPUT_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_INPUT_S, PKSPROPERTY_TUNER_INPUT_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_INPUT_S, ksmedia/PKSPROPERTY_TUNER_INPUT_S, stream.ksproperty_tuner_input_s, vidcapstruct_db1848a6-76f7-4f65-923e-cfd678a90b64.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSPROPERTY_TUNER_INPUT_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_INPUT_S, *PKSPROPERTY_TUNER_INPUT_S
---

# KSPROPERTY_TUNER_INPUT_S structure


## -description


The KSPROPERTY_TUNER_INPUT_S structure describes the input connection index of a tuner device for devices that support multiple inputs.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      InputIndex;
} KSPROPERTY_TUNER_INPUT_S, *PKSPROPERTY_TUNER_INPUT_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field InputIndex

Specifies the connection index to be used as the tuner input. This value should be in the range of 0 through (number of inputs-1).


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565851">KSPROPERTY_TUNER_INPUT</a>



 

 


