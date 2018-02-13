---
UID: NS:dot11wdi._WDI_TXRX_MPDU_PN
title: "_WDI_TXRX_MPDU_PN"
author: windows-driver-content
description: The WDI_TXRX_MPDU_PN union defines the parameters that are passed down to the TXRX component.
old-location: netvista\wdi_txrx_mpdu_pn.htm
old-project: netvista
ms.assetid: F03F5BE6-B2F2-4A9A-8D6D-1ACC9F08C890
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_TXRX_MPDU_PN union [Network Drivers Starting with Windows Vista], dot11wdi/WDI_TXRX_MPDU_PN, _WDI_TXRX_MPDU_PN, WDI_TXRX_MPDU_PN, netvista.wdi_txrx_mpdu_pn
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
-	WDI_TXRX_MPDU_PN
product: Windows
targetos: Windows
req.typenames: WDI_TXRX_MPDU_PN
---

# _WDI_TXRX_MPDU_PN structure


## -description


The 
  WDI_TXRX_MPDU_PN union defines the parameters that are passed down to the TXRX component.


## -syntax


````
typedef union _WDI_TXRX_MPDU_PN {
  UINT32 Pn24;
  UINT64 Pn48;
  UINT64 Pn128[2];
} WDI_TXRX_MPDU_PN;
````


## -struct-fields




### -field Pn24

WEP: 24-bit PN


### -field Pn48

TKIP or CCMP: 48-bit PN


### -field Pn128

WAPI: 128-bit PN

