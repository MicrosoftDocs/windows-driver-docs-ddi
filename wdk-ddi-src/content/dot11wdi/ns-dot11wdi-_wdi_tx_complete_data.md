---
UID: NS:dot11wdi._WDI_TX_COMPLETE_DATA
title: _WDI_TX_COMPLETE_DATA (dot11wdi.h)
description: The WDI_TX_COMPLETE_DATA structure defines TX completion data.
old-location: netvista\wdi_tx_complete_data.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_TX_COMPLETE_DATA structure"]
ms.keywords: "*PWDI_TX_COMPLETE_DATA, PWDI_TX_COMPLETE_DATA, PWDI_TX_COMPLETE_DATA structure pointer [Network Drivers Starting with Windows Vista], WDI_TX_COMPLETE_DATA, WDI_TX_COMPLETE_DATA structure [Network Drivers Starting with Windows Vista], _WDI_TX_COMPLETE_DATA, dot11wdi/PWDI_TX_COMPLETE_DATA, dot11wdi/WDI_TX_COMPLETE_DATA, netvista.wdi_tx_complete_data, netvista.wifi_tx_complete_data"
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
req.typenames: WDI_TX_COMPLETE_DATA, *PWDI_TX_COMPLETE_DATA
f1_keywords:
 - _WDI_TX_COMPLETE_DATA
 - dot11wdi/_WDI_TX_COMPLETE_DATA
 - PWDI_TX_COMPLETE_DATA
 - dot11wdi/PWDI_TX_COMPLETE_DATA
 - WDI_TX_COMPLETE_DATA
 - dot11wdi/WDI_TX_COMPLETE_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_TX_COMPLETE_DATA
 - PWDI_TX_COMPLETE_DATA
 - WDI_TX_COMPLETE_DATA
---

# _WDI_TX_COMPLETE_DATA structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_TX_COMPLETE_DATA structure defines TX completion data.

## -struct-fields

### -field SeqCtl

The value of the sequence control field from the frame transmission.

### -field PnLength

The MPDU PN length for the transmitted frame.

### -field RetryCount

The number of attempts to transmit the frame.

### -field wPad

This member is reserved.

### -field MpduPN

The MPDU PN.

### -field ReplayIHVReserved0

Reserved for IHV use.

### -field ReplayIHVReserved1

Reserved for IHV use.

