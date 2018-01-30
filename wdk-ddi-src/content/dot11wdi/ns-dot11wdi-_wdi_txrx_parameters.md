---
UID: NS:dot11wdi._WDI_TXRX_PARAMETERS
title: "_WDI_TXRX_PARAMETERS"
author: windows-driver-content
description: The WDI_TXRX_PARAMETERS structure defines the parameters that are passed down to the TXRX component.
old-location: netvista\wdi_txrx_parameters.htm
old-project: netvista
ms.assetid: 839a1c3d-ac9f-4723-a0f1-6610b763c32a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PWDI_TXRX_PARAMETERS, PWDI_TXRX_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], WDI_TXRX_PARAMETERS structure [Network Drivers Starting with Windows Vista], netvista.wifi_txrx_parameters, dot11wdi/PWDI_TXRX_PARAMETERS, WDI_TXRX_PARAMETERS, _WDI_TXRX_PARAMETERS, *PWDI_TXRX_PARAMETERS, netvista.wdi_txrx_parameters, dot11wdi/WDI_TXRX_PARAMETERS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	WDI_TXRX_PARAMETERS
product: Windows
targetos: Windows
req.typenames: WDI_TXRX_PARAMETERS, *PWDI_TXRX_PARAMETERS
---

# _WDI_TXRX_PARAMETERS structure


## -description


The 
  WDI_TXRX_PARAMETERS structure defines the parameters that are passed down to the TXRX component.


## -syntax


````
typedef struct _WDI_TXRX_PARAMETERS {
  WDI_TXRX_CAPABILITIES TxRxCapabilities;
} WDI_TXRX_PARAMETERS, *PWDI_TXRX_PARAMETERS;
````


## -struct-fields




### -field TxRxCapabilities

Specifies the TXRX capabilities.

