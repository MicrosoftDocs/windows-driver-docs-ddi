---
UID: NS:smclib._SMARTCARD_REPLY
title: _SMARTCARD_REPLY (smclib.h)
description: Describes the reply buffer received from the smart card.
old-location: smartcrd\smartcard_reply.htm
tech.root: smartcrd
ms.assetid: DB41648B-8812-4358-BECE-8029016E5631
ms.date: 02/22/2018
keywords: ["_SMARTCARD_REPLY structure"]
ms.keywords: "*PSMARTCARD_REPLY, PSMARTCARD_REPLY, PSMARTCARD_REPLY structure pointer [Smart Card Reader Devices], SMARTCARD_REPLY, SMARTCARD_REPLY structure [Smart Card Reader Devices], _SMARTCARD_REPLY, smartcrd.smartcard_reply, smclib/PSMARTCARD_REPLY, smclib/SMARTCARD_REPLY"
f1_keywords:
 - "smclib/SMARTCARD_REPLY"
 - "SMARTCARD_REPLY"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Smclib.h
api_name:
- SMARTCARD_REPLY
product:
- Windows
targetos: Windows
req.typenames: SMARTCARD_REPLY, *PSMARTCARD_REPLY
---

# _SMARTCARD_REPLY structure


## -description


Describes the reply buffer received from the smart card.   


## -struct-fields




### -field Buffer

Pointer to a buffer that  receives smart card data.


### -field BufferSize

Size of the buffer pointed to by <i>Buffer</i>.


### -field BufferLength

Number of bytes received from the card.


## -remarks



The client driver must receive data in this buffer and   adjust <i>BufferLength</i> to the number of received bytes. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/dn946592(v=vs.85)">SmcCxGetSmartcardReplyBuffer</a>
 

 

