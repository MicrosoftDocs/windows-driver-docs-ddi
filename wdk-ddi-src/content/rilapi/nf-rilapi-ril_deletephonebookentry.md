---
UID: NF:rilapi.RIL_DeletePhonebookEntry
title: RIL_DeletePhonebookEntry function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_deletephonebookentry.htm
old-project: netvista
ms.assetid: 110c542a-c98a-450d-b943-d8449dcac668
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapi/RIL_DeletePhonebookEntry, RIL_DeletePhonebookEntry method [Network Drivers Starting with Windows Vista], RIL_DeletePhonebookEntry, netvista.ril_deletephonebookentry
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
-	RIL_DeletePhonebookEntry
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_DeletePhonebookEntry function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_DeletePhonebookEntry(
   HRIL                         hRil,
   LPVOID                       lpContext,
   HUICCAPP                     hUiccApp,
   RILPHONEENTRYSTORELOCATION   dwStoreLocation,
   DWORD                        dwIndex,
   const RILUICCLOCKCREDENTIAL  lpLockVerification
);
````


## -parameters




### -param hRil


### -param lpContext


### -param hUiccApp


### -param dwStoreLocation


### -param dwIndex


### -param lpLockVerification


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



