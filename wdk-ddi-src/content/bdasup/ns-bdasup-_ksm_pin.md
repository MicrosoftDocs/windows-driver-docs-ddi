---
UID: NS:bdasup._KSM_PIN
title: "_KSM_PIN"
author: windows-driver-content
description: The KSM_PIN structure describes a method request to create or delete a pin factory for a filter.
old-location: stream\ksm_pin.htm
old-project: stream
ms.assetid: 7341af26-3c5c-4f33-b924-2e8098aeee7f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSM_PIN, ,, I, K, KSM_PIN, KSM_PIN structure [Streaming Media Devices], M, N, P, PKSM_PIN, PKSM_PIN structure pointer [Streaming Media Devices], S, _, _KSM_PIN, bdaref_029de0a4-0975-435c-990d-4b5cac00e003.xml, bdasup/KSM_PIN, bdasup/PKSM_PIN, stream.ksm_pin"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bdasup.h
apiname:
-	KSM_PIN
product: Windows
targetos: Windows
req.typenames: KSM_PIN, *PKSM_PIN
---

# _KSM_PIN structure


## -description


The KSM_PIN structure describes a method request to create or delete a pin factory for a filter. 


## -syntax


````
typedef struct _KSM_PIN {
  KSMETHOD Method;
  union {
    ULONG PinId;
    ULONG PinType;
  };
  ULONG    Reserved;
} KSM_PIN, *PKSM_PIN;
````


## -struct-fields




### -field Method

KSMETHOD structure that describes a method and request type of a method request.


### -field Reserved

Reserved.


#### - PinId

Member of the union in KSM_PIN that contains the identifier (ID) of a pin factory of a filter.


#### - PinType

Member of the union in KSM_PIN that contains the value that specifies the pin type.


## -remarks



When the network provider creates or deletes a pin for a filter using either KSMETHOD_BDA_CREATE_PIN_FACTORY or KSMETHOD_BDA_DELETE_PIN_FACTORY of the KSMETHODSETID_BdaDeviceConfiguration method set, the BDA minidriver for the filter gives that pin an ID. The ID for the pin is returned in KSM_PIN. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSM_PIN structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

