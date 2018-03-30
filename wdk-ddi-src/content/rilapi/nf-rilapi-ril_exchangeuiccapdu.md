---
UID: NF:rilapi.RIL_ExchangeUiccAPDU
title: RIL_ExchangeUiccAPDU function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_exchangeuiccapdu.htm
old-project: netvista
ms.assetid: e0d0eaa5-8f3a-4522-b99b-76f42402dae9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RIL_ExchangeUiccAPDU, RIL_ExchangeUiccAPDU method [Network Drivers Starting with Windows Vista], netvista.ril_exchangeuiccapdu, rilapi/RIL_ExchangeUiccAPDU
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
-	RIL_ExchangeUiccAPDU
product: Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
req.product: Windows 10 or later.
---

# RIL_ExchangeUiccAPDU function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -parameters




### -param hRil


### -param lpContext


### -param dwSlotIndex


### -param dwChannelId


### -param dwAPDULength


### -param bAPDU


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



