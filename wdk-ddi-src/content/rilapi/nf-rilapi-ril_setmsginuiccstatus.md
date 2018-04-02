---
UID: NF:rilapi.RIL_SetMsgInUiccStatus
title: RIL_SetMsgInUiccStatus function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setmsginuiccstatus.htm
old-project: netvista
ms.assetid: 0f24bddd-9e22-4710-9028-dbeeac29e2d5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RIL_SetMsgInUiccStatus, RIL_SetMsgInUiccStatus method [Network Drivers Starting with Windows Vista], netvista.ril_setmsginuiccstatus, rilapi/RIL_SetMsgInUiccStatus
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
-	RIL_SetMsgInUiccStatus
product: Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
req.product: Windows 10 or later.
---

# RIL_SetMsgInUiccStatus function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -parameters




### -param hRil


### -param lpContext


### -param hUiccApp


### -param dwIndex


### -param dwStatus


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



