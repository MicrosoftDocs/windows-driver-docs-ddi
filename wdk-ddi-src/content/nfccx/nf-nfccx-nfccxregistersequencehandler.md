---
UID: NF:nfccx.NfcCxRegisterSequenceHandler
title: NfcCxRegisterSequenceHandler function
author: windows-driver-content
description: Called by the client driver during initialization to register for handling specific sequences.
old-location: nfpdrivers\_nfccxregistersequencehandler.htm
old-project: nfpdrivers
ms.assetid: 30957475-D02B-434D-9FAB-BBCD5732DCA5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: NfcCxRegisterSequenceHandler, NfcCxRegisterSequenceHandler method [Near-Field Proximity Drivers], nfccx/NfcCxRegisterSequenceHandler, nfpdrivers._nfccxregistersequencehandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Nfccxstub.lib
req.dll: NfcCx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NfcCx.dll
api_name:
-	NfcCxRegisterSequenceHandler
product: Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---

# NfcCxRegisterSequenceHandler function


## -description


Called by the client driver during initialization to register for handling specific sequences.


## -parameters




### -param Device

A handle to a framework device object.


### -param Sequence

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn905563">NFC_CX_SEQUENCE</a>-typed enumerator.


### -param EvtNfcCxSequenceHandler

A pointer to an <a href="https://msdn.microsoft.com/6EB96A37-06B9-4655-AD69-375EE770F4DF">EvtNfcCxSequenceHandler</a> callback function. 


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.






## -see-also




<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NfcCxRegisterSequenceHandler method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

