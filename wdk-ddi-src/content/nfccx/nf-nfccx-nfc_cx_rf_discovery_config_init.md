---
UID: NF:nfccx.NFC_CX_RF_DISCOVERY_CONFIG_INIT
title: NFC_CX_RF_DISCOVERY_CONFIG_INIT function
author: windows-driver-content
description: The NFC_CX_RF_DISCOVERY_CONFIG_INIT function initializes the NFC_CX_RF_DISCOVERY_CONFIG structure.
old-location: nfpdrivers\nfc_cx_rf_discovery_config_init.htm
old-project: nfpdrivers
ms.assetid: C8A6A286-8F62-4A55-9AED-263317088706
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , C, D, E, F, G, I, N, NFC_CX_RF_DISCOVERY_CONFIG_INIT, NFC_CX_RF_DISCOVERY_CONFIG_INIT function [Near-Field Proximity Drivers], O, R, S, T, V, X, Y, _, nfccx/NFC_CX_RF_DISCOVERY_CONFIG_INIT, nfpdrivers.nfc_cx_rf_discovery_config_init"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Desktop
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
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	nfccxstub.lib
-	nfccxstub.dll
apiname:
-	NFC_CX_RF_DISCOVERY_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---

# NFC_CX_RF_DISCOVERY_CONFIG_INIT function


## -description


The NFC_CX_RF_DISCOVERY_CONFIG_INIT function initializes the <a href="..\nfccx\ns-nfccx-_nfc_cx_rf_discovery_config.md">NFC_CX_RF_DISCOVERY_CONFIG</a> structure.


## -syntax


````
VOID NFC_CX_RF_DISCOVERY_CONFIG_INIT(
  _Out_ PNFC_CX_RF_DISCOVERY_CONFIG Config
);
````


## -parameters




### -param Config [out]

A pointer to the NFC_CX_RF_DISCOVERY_CONFIG structure that the function initializes.


## -returns



This function does not return a value.




## -see-also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_RF_DISCOVERY_CONFIG_INIT function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

