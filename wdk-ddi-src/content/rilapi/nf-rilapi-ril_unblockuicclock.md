---
UID: NF:rilapi.RIL_UnblockUiccLock
title: RIL_UnblockUiccLock function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_unblockuicclock.htm
old-project: netvista
ms.assetid: a8cddfa1-b15e-4832-8c9c-12d378bc682d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_UnblockUiccLock method [Network Drivers Starting with Windows Vista], RIL_UnblockUiccLock, rilapi/RIL_UnblockUiccLock, netvista.ril_unblockuicclock
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
-	RIL_UnblockUiccLock
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_UnblockUiccLock function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_UnblockUiccLock(
   HRIL                         hRil,
   LPVOID                       lpContext,
   const RILUICCLOCKCREDENTIAL  lpLockCredential,
   LPCSTR                       lpszNewPassword
);
````


## -parameters




#### - hRil



#### - lpContext



#### - lpLockCredential



#### - lpszNewPassword



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


