---
UID: NS:dot11wdi._WDI_TXRX_TARGET_CONFIGURATION
title: _WDI_TXRX_TARGET_CONFIGURATION (dot11wdi.h)
description: The WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration.
old-location: netvista\wdi_txrx_target_configuration.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_TXRX_TARGET_CONFIGURATION structure"]
ms.keywords: "*PWDI_TXRX_TARGET_CONFIGURATION, PWDI_TXRX_TARGET_CONFIGURATION, PWDI_TXRX_TARGET_CONFIGURATION structure pointer [Network Drivers Starting with Windows Vista], WDI_TXRX_TARGET_CONFIGURATION, WDI_TXRX_TARGET_CONFIGURATION structure [Network Drivers Starting with Windows Vista], _WDI_TXRX_TARGET_CONFIGURATION, dot11wdi/PWDI_TXRX_TARGET_CONFIGURATION, dot11wdi/WDI_TXRX_TARGET_CONFIGURATION, netvista.wdi_txrx_target_configuration, netvista.wifi_txrx_target_configuration"
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
targetos: Windows
req.typenames: WDI_TXRX_TARGET_CONFIGURATION, *PWDI_TXRX_TARGET_CONFIGURATION
f1_keywords:
 - _WDI_TXRX_TARGET_CONFIGURATION
 - dot11wdi/_WDI_TXRX_TARGET_CONFIGURATION
 - PWDI_TXRX_TARGET_CONFIGURATION
 - dot11wdi/PWDI_TXRX_TARGET_CONFIGURATION
 - WDI_TXRX_TARGET_CONFIGURATION
 - dot11wdi/WDI_TXRX_TARGET_CONFIGURATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_TXRX_TARGET_CONFIGURATION
 - PWDI_TXRX_TARGET_CONFIGURATION
 - WDI_TXRX_TARGET_CONFIGURATION
---

# _WDI_TXRX_TARGET_CONFIGURATION structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The 
  WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration.

## -struct-fields

### -field TxRxParams

Specifies the TXRX parameters.

### -field MaxNumPorts

Specifies the maximum number of ports.

### -field MaxNumPeers

Specifies the maximum number of peers.

