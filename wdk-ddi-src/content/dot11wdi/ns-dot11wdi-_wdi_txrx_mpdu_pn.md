---
UID: NS:dot11wdi._WDI_TXRX_MPDU_PN
title: _WDI_TXRX_MPDU_PN (dot11wdi.h)
description: The WDI_TXRX_MPDU_PN union defines the parameters that are passed down to the TXRX component.
old-location: netvista\wdi_txrx_mpdu_pn.htm
tech.root: netvista
ms.assetid: F03F5BE6-B2F2-4A9A-8D6D-1ACC9F08C890
ms.date: 05/02/2018
keywords: ["_WDI_TXRX_MPDU_PN structure"]
ms.keywords: WDI_TXRX_MPDU_PN, WDI_TXRX_MPDU_PN union [Network Drivers Starting with Windows Vista], _WDI_TXRX_MPDU_PN, dot11wdi/WDI_TXRX_MPDU_PN, netvista.wdi_txrx_mpdu_pn
f1_keywords:
 - "dot11wdi/WDI_TXRX_MPDU_PN"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dot11wdi.h
api_name:
- WDI_TXRX_MPDU_PN
product:
- Windows
targetos: Windows
req.typenames: WDI_TXRX_MPDU_PN
---

# _WDI_TXRX_MPDU_PN structure


## -description


The 
  WDI_TXRX_MPDU_PN union defines the parameters that are passed down to the TXRX component.


## -struct-fields




### -field Pn24

WEP: 24-bit PN


### -field Pn48

TKIP or CCMP: 48-bit PN


### -field Pn128

WAPI: 128-bit PN

