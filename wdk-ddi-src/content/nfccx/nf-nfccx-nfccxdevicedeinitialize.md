---
UID: NF:nfccx.NfcCxDeviceDeinitialize
title: NfcCxDeviceDeinitialize function
author: windows-driver-content
description: Called by the client driver after a WDF device has been created during the AddDevice routine.
old-location: nfpdrivers\_nfccxdevicedeinitialize.htm
old-project: nfpdrivers
ms.assetid: 1E1AC024-D628-4E31-80EF-8E929B8449FE
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: NfcCxDeviceDeinitialize method [Near-Field Proximity Drivers], nfpdrivers._nfccxdevicedeinitialize, NfcCxDeviceDeinitialize, nfccx/NfcCxDeviceDeinitialize
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
req.lib: Nfccsstub.lib
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
-	NfcCxDeviceDeinitialize
product: Windows
targetos: Windows
req.typenames: "*PNFC_CX_TRANSPORT_TYPE, NFC_CX_TRANSPORT_TYPE"
---

# NfcCxDeviceDeinitialize function


## -description


Called by the client driver after a WDF device has been created during the AddDevice routine.


## -syntax


````
NTSTATUS NfcCxDeviceDeinitialize(
   WDFDEVICE Device
);
````


## -parameters




### -param Device

A handle to a framework device object.


## -returns


If the operation succeeds, the function returns STATUS_SUCCESS.



## -see-also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NfcCxDeviceDeinitialize method%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

