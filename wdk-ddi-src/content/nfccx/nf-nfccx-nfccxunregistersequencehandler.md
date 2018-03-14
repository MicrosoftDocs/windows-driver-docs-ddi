---
UID: NF:nfccx.NfcCxUnregisterSequenceHandler
title: NfcCxUnregisterSequenceHandler function
author: windows-driver-content
description: Called by the client driver during device shutdown to unregister for the previously registered sequence handler callback.
old-location: nfpdrivers\_nfccxunregistersequencehandler.htm
old-project: nfpdrivers
ms.assetid: 689BF221-22CA-43B4-A5EB-ECE0B78F520B
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: NfcCxUnregisterSequenceHandler, NfcCxUnregisterSequenceHandler method [Near-Field Proximity Drivers], nfccx/NfcCxUnregisterSequenceHandler, nfpdrivers._nfccxunregistersequencehandler
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
-	NfcCxUnregisterSequenceHandler
product: Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---

# NfcCxUnregisterSequenceHandler function


## -description


Called by the client driver during device shutdown to unregister for the previously registered sequence handler callback.


## -syntax


````
NTSTATUS NfcCxUnregisterSequenceHandler(
   WDFDEVICE       Device,
   NFC_CX_SEQUENCE Sequence
);
````


## -parameters




### -param Device

A handle to a framework device object.


### -param Sequence

An <a href="..\nfccx\ne-nfccx-_nfc_cx_sequence.md">NFC_CX_SEQUENCE</a>-typed enumerator.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.






## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 


