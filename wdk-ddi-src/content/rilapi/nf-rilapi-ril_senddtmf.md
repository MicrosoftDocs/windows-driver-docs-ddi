---
UID: NF:rilapi.RIL_SendDTMF
title: RIL_SendDTMF function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_senddtmf.htm
tech.root: netvista
ms.assetid: 4091a37e-5115-4213-9242-76b119ad28fc
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: RIL_SendDTMF, RIL_SendDTMF method [Network Drivers Starting with Windows Vista], netvista.ril_senddtmf, rilapi/RIL_SendDTMF
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
-	RIL_SendDTMF
product:
- Windows
targetos: Windows
req.typenames: 
---

# RIL_SendDTMF function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -parameters




### -param hRil


### -param lpContext


### -param dwExecutor


### -param lpszChars


### -param dwDigitOnTimeMs


### -param dwDigitOffTimeMs


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



