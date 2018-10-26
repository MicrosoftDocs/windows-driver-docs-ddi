---
UID: NF:rilapi.RIL_ChangeCallBarringPassword
title: RIL_ChangeCallBarringPassword function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_changecallbarringpassword.htm
tech.root: netvista
ms.assetid: f312e955-c8a5-4642-ac8a-a0173f034a63
ms.date: 05/02/2018
ms.keywords: RIL_ChangeCallBarringPassword, RIL_ChangeCallBarringPassword method [Network Drivers Starting with Windows Vista], netvista.ril_changecallbarringpassword, rilapi/RIL_ChangeCallBarringPassword
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapi.h
api_name:
-	RIL_ChangeCallBarringPassword
product:
- Windows
targetos: Windows
req.typenames: 
---

# RIL_ChangeCallBarringPassword function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


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



