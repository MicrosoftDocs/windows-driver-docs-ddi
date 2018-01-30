---
UID: NF:rilapi.RIL_SetUiccLockEnabled
title: RIL_SetUiccLockEnabled function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setuicclockenabled.htm
old-project: netvista
ms.assetid: eb422fec-8cc3-42b8-9caf-21fd135df7a1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_setuicclockenabled, RIL_SetUiccLockEnabled method [Network Drivers Starting with Windows Vista], RIL_SetUiccLockEnabled, rilapi/RIL_SetUiccLockEnabled
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
-	RIL_SetUiccLockEnabled
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_SetUiccLockEnabled function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SetUiccLockEnabled(
   HRIL                         hRil,
   LPVOID                       lpContext,
   const RILUICCLOCKCREDENTIAL  lpLockCredential,
   BOOL                         fEnable
);
````


## -parameters




### -param hRil



### -param lpContext



### -param lpLockCredential



### -param fEnable



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


