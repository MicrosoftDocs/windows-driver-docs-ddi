---
UID: NS:bdamedia._KSM_BDA_PIN
title: "_KSM_BDA_PIN"
description: The KSM_BDA_PIN structure describes a method request to create or delete a pin factory for a filter.
old-location: stream\ksm_bda_pin.htm
tech.root: stream
ms.assetid: 7e7778ba-cf4f-44e8-91ce-c53458d3db9a
ms.date: 04/23/2018
ms.keywords: "*PKSM_BDA_PIN, KSM_BDA_PIN, KSM_BDA_PIN structure [Streaming Media Devices], PKSM_BDA_PIN, PKSM_BDA_PIN structure pointer [Streaming Media Devices], _KSM_BDA_PIN, bdamedia/KSM_BDA_PIN, bdamedia/PKSM_BDA_PIN, bdaref_190ab329-704e-472a-926c-1aa04d4b6df5.xml, stream.ksm_bda_pin"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bdamedia.h
api_name:
-	KSM_BDA_PIN
product:
- Windows
targetos: Windows
req.typenames: KSM_BDA_PIN, *PKSM_BDA_PIN
---

# _KSM_BDA_PIN structure


## -description


The KSM_BDA_PIN structure describes a method request to create or delete a pin factory for a filter. 


## -struct-fields




### -field Method

KSMETHOD structure that describes a method and request type of a method request.


### -field PinId

Member of the union in KSM_BDA_PIN that contains the identifier (ID) of a pin factory of a filter.


### -field PinType

Member of the union in KSM_BDA_PIN that contains the value that specifies the pin type.


### -field Reserved

Reserved.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>
 

 

