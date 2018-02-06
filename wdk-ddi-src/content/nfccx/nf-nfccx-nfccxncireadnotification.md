---
UID: NF:nfccx.NfcCxNciReadNotification
title: NfcCxNciReadNotification function
author: windows-driver-content
description: Called by the client driver when a read packet is available.
old-location: nfpdrivers\_nfccxncireadnotification.htm
old-project: nfpdrivers
ms.assetid: 0D2FB16D-ABBC-428F-95D4-4B17E262D115
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: NfcCxNciReadNotification, NfcCxNciReadNotification method [Near-Field Proximity Drivers], nfpdrivers._nfccxncireadnotification, nfccx/NfcCxNciReadNotification
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NfcCx.dll
apiname:
-	NfcCxNciReadNotification
product: Windows
targetos: Windows
req.typenames: "*PNFC_CX_TRANSPORT_TYPE, NFC_CX_TRANSPORT_TYPE"
---

# NfcCxNciReadNotification function


## -description


Called by the client driver when a read packet is available. The WDFMEMORY can be deallocated by the client driver after completion of the call. While NFC CXs implementation will quickly process this call, it is expected that the client driver doesnt make this call from the context of an ISR. It is recommend that the client driver issues this call from the ISR work-item.


## -syntax


````
NTSTATUS NfcCxNciReadNotification(
   WDFDEVICE Device,
   WDFMEMORY Memory
);
````


## -parameters




### -param Device

A handle to a framework device object.


### -param Memory

A handle to a framework memory object.


## -returns


If the operation succeeds, the function returns STATUS_SUCCESS.





## -see-also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NfcCxNciReadNotification method%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

