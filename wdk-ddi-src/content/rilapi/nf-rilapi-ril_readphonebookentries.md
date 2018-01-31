---
UID: NF:rilapi.RIL_ReadPhonebookEntries
title: RIL_ReadPhonebookEntries function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_readphonebookentries.htm
old-project: netvista
ms.assetid: 3da05f28-a6de-4dad-a978-0439f3244bbb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_readphonebookentries, RIL_ReadPhonebookEntries, rilapi/RIL_ReadPhonebookEntries, RIL_ReadPhonebookEntries method [Network Drivers Starting with Windows Vista]
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
-	RIL_ReadPhonebookEntries
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_ReadPhonebookEntries function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_ReadPhonebookEntries(
   HRIL                       hRil,
   LPVOID                     lpContext,
   HUICCAPP                   hUiccApp,
   RILPHONEENTRYSTORELOCATION dwStoreLocation,
   DWORD                      dwStartIndex,
   DWORD                      dwEndIndex
);
````


## -parameters




#### - hRil



#### - lpContext



#### - hUiccApp



#### - dwStoreLocation



#### - dwStartIndex



#### - dwEndIndex



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


