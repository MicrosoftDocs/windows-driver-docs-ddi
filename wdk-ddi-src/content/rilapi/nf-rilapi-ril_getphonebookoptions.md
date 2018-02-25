---
UID: NF:rilapi.RIL_GetPhonebookOptions
title: RIL_GetPhonebookOptions function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getphonebookoptions.htm
old-project: netvista
ms.assetid: 7d8ff1cc-e5d6-473b-bc16-e87468bb546c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , G, I, L, O, P, R, RIL_GetPhonebookOptions, RIL_GetPhonebookOptions method [Network Drivers Starting with Windows Vista], _, b, e, h, i, k, n, netvista.ril_getphonebookoptions, o, p, rilapi/RIL_GetPhonebookOptions, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapi.h
apiname:
-	RIL_GetPhonebookOptions
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetPhonebookOptions function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetPhonebookOptions(
   HRIL                       hRil,
   LPVOID                     lpContext,
   HUICCAPP                   hUiccApp,
   RILPHONEENTRYSTORELOCATION dwStoreLocation
);
````


## -parameters




### -param hRil


### -param lpContext


### -param hUiccApp


### -param dwStoreLocation


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



