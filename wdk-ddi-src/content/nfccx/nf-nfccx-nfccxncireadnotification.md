---
UID: NF:nfccx.NfcCxNciReadNotification
title: NfcCxNciReadNotification function (nfccx.h)
description: Called by the client driver when a read packet is available.
old-location: nfpdrivers\_nfccxncireadnotification.htm
tech.root: nfpdrivers
ms.assetid: 0D2FB16D-ABBC-428F-95D4-4B17E262D115
ms.date: 02/15/2018
ms.keywords: NfcCxNciReadNotification, NfcCxNciReadNotification method [Near-Field Proximity Drivers], nfccx/NfcCxNciReadNotification, nfpdrivers._nfccxncireadnotification
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NfcCx.dll
api_name:
- NfcCxNciReadNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# NfcCxNciReadNotification function


## -description


Called by the client driver when a read packet is available. The WDFMEMORY can be deallocated by the client driver after completion of the call. While NFC CXs implementation will quickly process this call, it is expected that the client driver doesnt make this call from the context of an ISR. It is recommend that the client driver issues this call from the ISR work-item.


## -parameters




### -param Device

A handle to a framework device object.


### -param Memory

A handle to a framework memory object.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

