---
UID: NS:smclib._SMARTCARD_REQUEST
title: "_SMARTCARD_REQUEST"
author: windows-driver-content
description: Describes the request buffer that contains data to send to the card.
old-location: smartcrd\smartcard_request.htm
old-project: smartcrd
ms.assetid: B5FF5B24-12E6-424A-B09A-4B0572621088
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SMARTCARD_REQUEST structure [Smart Card Reader Devices], PSMARTCARD_REQUEST structure pointer [Smart Card Reader Devices], PSMARTCARD_REQUEST, smartcrd.smartcard_request, smclib/SMARTCARD_REQUEST, smclib/PSMARTCARD_REQUEST, SMARTCARD_REQUEST, _SMARTCARD_REQUEST, *PSMARTCARD_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Smclib.h
apiname:
-	SMARTCARD_REQUEST
product: Windows
targetos: Windows
req.typenames: "*PSMARTCARD_REQUEST, SMARTCARD_REQUEST"
req.product: Windows 10 or later.
---

# _SMARTCARD_REQUEST structure


## -description


Describes the request buffer that contains data to send to the card. 


## -syntax


````
typedef struct _SMARTCARD_REPLY {
  PUCHAR 	Buffer;
  ULONG  BufferSize;
  ULONG  BufferLength;
} SMARTCARD_REQUEST, *PSMARTCARD_REQUEST;
````


## -struct-fields




### -field Buffer

Pointer to a buffer that  contains data to send.


### -field BufferSize

Size of the buffer pointed to by <i>Buffer</i>.


### -field BufferLength

Number of bytes required for this command.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946593">SmcCxGetSmartcardRequestBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [smartcrd\smartcrd]:%20SMARTCARD_REQUEST structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

