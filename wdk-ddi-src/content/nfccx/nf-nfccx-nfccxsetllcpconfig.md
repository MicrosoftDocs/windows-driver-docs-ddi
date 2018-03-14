---
UID: NF:nfccx.NfcCxSetLlcpConfig
title: NfcCxSetLlcpConfig function
author: windows-driver-content
description: Called by the client driver to configure the LLCP parameters.
old-location: nfpdrivers\_nfccxsetllcpconfig.htm
old-project: nfpdrivers
ms.assetid: 8208F61E-DFD9-4AA8-B225-BEB35F80F621
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: NfcCxSetLlcpConfig, NfcCxSetLlcpConfig method [Near-Field Proximity Drivers], nfccx/NfcCxSetLlcpConfig, nfpdrivers._nfccxsetllcpconfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	NfcCxSetLlcpConfig
product: Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---

# NfcCxSetLlcpConfig function


## -description


Called by the client driver to configure the LLCP parameters.


## -syntax


````
NTSTATUS NfcCxSetLlcpConfig(
   WDFDEVICE            Device,
   PCNFC_CX_LLCP_CONFIG Config
);
````


## -parameters




### -param Device

A handle to a framework device object.


### -param Config

A pointer to an <a href="..\nfccx\ns-nfccx-_nfc_cx_llcp_config.md">NFC_CX_LLCP_CONFIG</a> structure.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.




## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 


