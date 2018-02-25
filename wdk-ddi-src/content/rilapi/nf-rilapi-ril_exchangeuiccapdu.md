---
UID: NF:rilapi.RIL_ExchangeUiccAPDU
title: RIL_ExchangeUiccAPDU function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_exchangeuiccapdu.htm
old-project: netvista
ms.assetid: e0d0eaa5-8f3a-4522-b99b-76f42402dae9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, D, E, I, L, P, R, RIL_ExchangeUiccAPDU, RIL_ExchangeUiccAPDU method [Network Drivers Starting with Windows Vista], U, _, a, c, e, g, h, i, n, netvista.ril_exchangeuiccapdu, rilapi/RIL_ExchangeUiccAPDU, x"
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
-	RIL_ExchangeUiccAPDU
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_ExchangeUiccAPDU function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_ExchangeUiccAPDU(
   HRIL        hRil,
   LPVOID      lpContext,
   DWORD       dwSlotIndex,
   DWORD       dwChannelId,
   DWORD       dwAPDULength,
   const BYTE  bAPDU
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwSlotIndex


### -param dwChannelId


### -param dwAPDULength


### -param bAPDU


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



