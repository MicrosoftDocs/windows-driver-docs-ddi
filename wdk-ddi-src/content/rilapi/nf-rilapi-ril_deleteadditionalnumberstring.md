---
UID: NF:rilapi.RIL_DeleteAdditionalNumberString
title: RIL_DeleteAdditionalNumberString function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_deleteadditionalnumberstring.htm
old-project: netvista
ms.assetid: 6d115616-85d4-43f8-b0c8-ea5b5c2e4eff
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_DeleteAdditionalNumberString, netvista.ril_deleteadditionalnumberstring, RIL_DeleteAdditionalNumberString, RIL_DeleteAdditionalNumberString method [Network Drivers Starting with Windows Vista]
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
-	RIL_DeleteAdditionalNumberString
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_DeleteAdditionalNumberString function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_DeleteAdditionalNumberString(
   HRIL     hRil,
   LPVOID   lpContext,
   HUICCAPP hUiccApp,
   DWORD    dwNumId
);
````


## -parameters




### -param hRil



### -param lpContext



### -param hUiccApp



### -param dwNumId



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


