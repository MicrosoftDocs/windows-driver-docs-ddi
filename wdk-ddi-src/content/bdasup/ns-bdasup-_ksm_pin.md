---
UID: NS:bdasup._KSM_PIN
title: _KSM_PIN (bdasup.h)
description: The KSM_PIN structure describes a method request to create or delete a pin factory for a filter.
old-location: stream\ksm_pin.htm
tech.root: stream
ms.assetid: 7341af26-3c5c-4f33-b924-2e8098aeee7f
ms.date: 04/23/2018
ms.keywords: "*PKSM_PIN, KSM_PIN, KSM_PIN structure [Streaming Media Devices], PKSM_PIN, PKSM_PIN structure pointer [Streaming Media Devices], _KSM_PIN, bdaref_029de0a4-0975-435c-990d-4b5cac00e003.xml, bdasup/KSM_PIN, bdasup/PKSM_PIN, stream.ksm_pin"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bdasup.h
api_name:
-	KSM_PIN
product:
- Windows
targetos: Windows
req.typenames: KSM_PIN, *PKSM_PIN
---

# _KSM_PIN structure


## -description


The KSM_PIN structure describes a method request to create or delete a pin factory for a filter. 


## -struct-fields




### -field Method

KSMETHOD structure that describes a method and request type of a method request.


### -field PinId

Member of the union in KSM_PIN that contains the identifier (ID) of a pin factory of a filter.


### -field PinType

Member of the union in KSM_PIN that contains the value that specifies the pin type.


### -field Reserved

Reserved.


## -remarks



When the network provider creates or deletes a pin for a filter using either KSMETHOD_BDA_CREATE_PIN_FACTORY or KSMETHOD_BDA_DELETE_PIN_FACTORY of the KSMETHODSETID_BdaDeviceConfiguration method set, the BDA minidriver for the filter gives that pin an ID. The ID for the pin is returned in KSM_PIN. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>
 

 

