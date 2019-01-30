---
UID: NS:smclib._SMARTCARD_REQUEST
title: "_SMARTCARD_REQUEST" (smclib.h)
description: Describes the request buffer that contains data to send to the card.
old-location: smartcrd\smartcard_request.htm
tech.root: smartcrd
ms.assetid: B5FF5B24-12E6-424A-B09A-4B0572621088
ms.date: 02/22/2018
ms.keywords: "*PSMARTCARD_REQUEST, PSMARTCARD_REQUEST, PSMARTCARD_REQUEST structure pointer [Smart Card Reader Devices], SMARTCARD_REQUEST, SMARTCARD_REQUEST structure [Smart Card Reader Devices], _SMARTCARD_REQUEST, smartcrd.smartcard_request, smclib/PSMARTCARD_REQUEST, smclib/SMARTCARD_REQUEST"
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
-	Smclib.h
api_name:
-	SMARTCARD_REQUEST
product:
- Windows
targetos: Windows
req.typenames: SMARTCARD_REQUEST, *PSMARTCARD_REQUEST
---

# _SMARTCARD_REQUEST structure


## -description


Describes the request buffer that contains data to send to the card. 


## -struct-fields




### -field Buffer

Pointer to a buffer that  contains data to send.


### -field BufferSize

Size of the buffer pointed to by <i>Buffer</i>.


### -field BufferLength

Number of bytes required for this command.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn946593">SmcCxGetSmartcardRequestBuffer</a>
 

 

