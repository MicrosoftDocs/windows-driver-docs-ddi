---
UID: NF:rilapi.RIL_SendMsgAck
title: RIL_SendMsgAck function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_sendmsgack.htm
old-project: netvista
ms.assetid: 472ae963-1680-47f8-8802-83453d0c1413
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RIL_SendMsgAck
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
req.alt-api: RIL_SendMsgAck
req.alt-loc: rilapi.h
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
req.typenames: *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SendMsgAck function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_SendMsgAck(
   HRIL            hRil,
   LPVOID          lpContext,
   DWORD           dwExecutor,
   HUICCAPP        hUiccApp,
   DWORD           dwAckID,
   RILMSGACKSTATUS dwMsgStatus,
   RILSMSFORMAT    dwSmsFormat,
   RILSMSACKOPT    dwOptions
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param dwExecutor 


### -param hUiccApp 


### -param dwAckID 


### -param dwMsgStatus 


### -param dwSmsFormat 


### -param dwOptions 


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
