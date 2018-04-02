---
UID: NF:rilapi.RIL_SetUiccLockEnabled
title: RIL_SetUiccLockEnabled function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setuicclockenabled.htm
old-project: netvista
ms.assetid: eb422fec-8cc3-42b8-9caf-21fd135df7a1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RIL_SetUiccLockEnabled, RIL_SetUiccLockEnabled method [Network Drivers Starting with Windows Vista], netvista.ril_setuicclockenabled, rilapi/RIL_SetUiccLockEnabled
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
-	RIL_SetUiccLockEnabled
product:
- Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
req.product: Windows 10 or later.
---

# RIL_SetUiccLockEnabled function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -parameters




### -param hRil


### -param lpContext


### -param lpLockCredential


### -param fEnable


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



