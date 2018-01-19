---
UID: NS:dot11wdi._WDI_TXRX_TARGET_CONFIGURATION
title: _WDI_TXRX_TARGET_CONFIGURATION
author: windows-driver-content
description: The WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration.
old-location: netvista\wdi_txrx_target_configuration.htm
old-project: netvista
ms.assetid: 5a2d8bdf-cfc2-4724-aab3-0277edb477e7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_TXRX_TARGET_CONFIGURATION, *PWDI_TXRX_TARGET_CONFIGURATION, WDI_TXRX_TARGET_CONFIGURATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_TXRX_TARGET_CONFIGURATION
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
req.typenames: *PWDI_TXRX_TARGET_CONFIGURATION, WDI_TXRX_TARGET_CONFIGURATION
---

# _WDI_TXRX_TARGET_CONFIGURATION structure



## -description
The 
  WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration.



## -syntax

````
typedef struct _WDI_TXRX_TARGET_CONFIGURATION {
  WDI_TXRX_PARAMETERS TxRxParams;
  UINT8               MaxNumPorts;
  UINT8               MaxNumPeers;
} WDI_TXRX_TARGET_CONFIGURATION, *PWDI_TXRX_TARGET_CONFIGURATION;
````


## -struct-fields

### -field TxRxParams

Specifies the TXRX parameters.


### -field MaxNumPorts

Specifies the maximum number of ports.


### -field MaxNumPeers

Specifies the maximum number of peers.


## -remarks
