---
UID: NS:dot11wdi._TAL_TXRX_PARAMETERS
title: _TAL_TXRX_PARAMETERS (dot11wdi.h)
description: The TAL_TXRX_PARAMETERS structure defines the TAL TXRX parameters.
old-location: netvista\tal_txrx_parameters.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["TAL_TXRX_PARAMETERS structure"]
ms.keywords: "*PTAL_TXRX_PARAMETERS, PTAL_TXRX_PARAMETERS, PTAL_TXRX_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], TAL_TXRX_PARAMETERS, TAL_TXRX_PARAMETERS structure [Network Drivers Starting with Windows Vista], _TAL_TXRX_PARAMETERS, dot11wdi/PTAL_TXRX_PARAMETERS, dot11wdi/TAL_TXRX_PARAMETERS, netvista.tal_txrx_parameters"
req.header: dot11wdi.h
req.include-header: Ndis.h
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
targetos: Windows
req.typenames: TAL_TXRX_PARAMETERS, *PTAL_TXRX_PARAMETERS
f1_keywords:
 - _TAL_TXRX_PARAMETERS
 - dot11wdi/_TAL_TXRX_PARAMETERS
 - PTAL_TXRX_PARAMETERS
 - dot11wdi/PTAL_TXRX_PARAMETERS
 - TAL_TXRX_PARAMETERS
 - dot11wdi/TAL_TXRX_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _TAL_TXRX_PARAMETERS
 - PTAL_TXRX_PARAMETERS
 - TAL_TXRX_PARAMETERS
---

# _TAL_TXRX_PARAMETERS structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The 
  TAL_TXRX_PARAMETERS structure defines the TAL TXRX parameters.

## -struct-fields

### -field MaxOutstandingTransfers

Specifies the maximum number of outstanding  frame transfers to the target. No further frames are transferred until a transfer complete indication is received from the target/TAL.

