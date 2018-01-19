---
UID: NS:smclib._SMARTCARD_REPLY
title: _SMARTCARD_REPLY
author: windows-driver-content
description: Describes the reply buffer received from the smart card.
old-location: smartcrd\smartcard_reply.htm
old-project: smartcrd
ms.assetid: DB41648B-8812-4358-BECE-8029016E5631
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SMARTCARD_REPLY, SMARTCARD_REPLY, *PSMARTCARD_REPLY
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
req.alt-api: SMARTCARD_REPLY
req.alt-loc: Smclib.h
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
req.typenames: SMARTCARD_REPLY, *PSMARTCARD_REPLY
req.product: Windows 10 or later.
---

# _SMARTCARD_REPLY structure



## -description
Describes the reply buffer received from the smart card.   



## -syntax

````
typedef struct _SMARTCARD_REPLY {
  PUCHAR 	Buffer;
  ULONG  BufferSize;
  ULONG  BufferLength;
} SMARTCARD_REPLY, *PSMARTCARD_REPLY;
````


## -struct-fields

### -field 	Buffer

Pointer to a buffer that  receives smart card data.


### -field BufferSize

Size of the buffer pointed to by <i>Buffer</i>.


### -field BufferLength

Number of bytes received from the card.


## -remarks
The client driver must receive data in this buffer and   adjust <i>BufferLength</i> to the number of received bytes. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946592">SmcCxGetSmartcardReplyBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [smartcrd\smartcrd]:%20SMARTCARD_REPLY structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

