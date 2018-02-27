---
UID: NF:rilapi.RIL_SetCellBroadcastMsgConfig
title: RIL_SetCellBroadcastMsgConfig function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setcellbroadcastmsgconfig.htm
old-project: netvista
ms.assetid: c2b7b9b7-a76f-4bd9-bf25-edb5c103a578
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_SetCellBroadcastMsgConfig, RIL_SetCellBroadcastMsgConfig method [Network Drivers Starting with Windows Vista], netvista.ril_setcellbroadcastmsgconfig, rilapi/RIL_SetCellBroadcastMsgConfig
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
-	RIL_SetCellBroadcastMsgConfig
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SetCellBroadcastMsgConfig function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SetCellBroadcastMsgConfig(
   HRIL                  hRil,
   LPVOID                lpContext,
   HUICCAPP              hUiccApp,
   const RILCBMSGCONFIG  lpCbMsgConfigInfo
);
````


## -parameters




### -param hRil


### -param lpContext


### -param hUiccApp


### -param lpCbMsgConfigInfo


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



