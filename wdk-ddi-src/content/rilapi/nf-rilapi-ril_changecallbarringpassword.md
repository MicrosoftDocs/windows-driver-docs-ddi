---
UID: NF:rilapi.RIL_ChangeCallBarringPassword
title: RIL_ChangeCallBarringPassword function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_changecallbarringpassword.htm
old-project: netvista
ms.assetid: f312e955-c8a5-4642-ac8a-a0173f034a63
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_ChangeCallBarringPassword, netvista.ril_changecallbarringpassword, RIL_ChangeCallBarringPassword method [Network Drivers Starting with Windows Vista], RIL_ChangeCallBarringPassword
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
-	RIL_ChangeCallBarringPassword
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_ChangeCallBarringPassword function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_ChangeCallBarringPassword(
   HRIL                           hRil,
   LPVOID                         lpContext,
   DWORD                          dwExecutor,
   RILCALLBARRINGSTATUSPARAMSTYPE dwType,
   LPCSTR                         lpwszOldPassword,
   LPCSTR                         lpwszNewPassword,
   LPCSTR                         lpszConfirmPassword
);
````


## -parameters




### -param hRil



### -param lpContext



### -param dwExecutor



### -param dwType



### -param lpwszOldPassword



### -param lpwszNewPassword



### -param lpszConfirmPassword



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


