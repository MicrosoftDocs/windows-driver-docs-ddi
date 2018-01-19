---
UID: NS:dot11wdi._TAL_TXRX_PARAMETERS
title: _TAL_TXRX_PARAMETERS
author: windows-driver-content
description: The TAL_TXRX_PARAMETERS structure defines the TAL TXRX parameters.
old-location: netvista\tal_txrx_parameters.htm
old-project: netvista
ms.assetid: 44f5c907-7368-43ea-b581-3b9ecf25c611
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _TAL_TXRX_PARAMETERS, TAL_TXRX_PARAMETERS, *PTAL_TXRX_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TAL_TXRX_PARAMETERS
req.alt-loc: dot11wdi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: TAL_TXRX_PARAMETERS, *PTAL_TXRX_PARAMETERS
---

# _TAL_TXRX_PARAMETERS structure



## -description
The 
  TAL_TXRX_PARAMETERS structure defines the TAL TXRX parameters.



## -syntax

````
typedef struct _TAL_TXRX_PARAMETERS {
  UINT16 MaxOutstandingTransfers;
} TAL_TXRX_PARAMETERS, *PTAL_TXRX_PARAMETERS;
````


## -struct-fields

### -field MaxOutstandingTransfers

Specifies the maximum number of outstanding  frame transfers to the target. No further frames are transferred until a transfer complete indication is received from the target/TAL.


## -remarks
