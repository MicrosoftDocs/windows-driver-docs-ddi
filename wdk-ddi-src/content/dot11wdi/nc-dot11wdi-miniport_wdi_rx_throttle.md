---
UID: NC:dot11wdi.MINIPORT_WDI_RX_THROTTLE
title: MINIPORT_WDI_RX_THROTTLE (dot11wdi.h)
description: The MiniportWdiRxThrottle handler function tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs.
old-location: netvista\miniportwdirxthrottle.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_RX_THROTTLE callback function"]
ms.keywords: MINIPORT_WDI_RX_THROTTLE, MINIPORT_WDI_RX_THROTTLE callback, MiniportWdiRxThrottle, MiniportWdiRxThrottle callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxThrottle, netvista.miniportwdirxthrottle
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
req.typenames: 
f1_keywords:
 - MINIPORT_WDI_RX_THROTTLE
 - dot11wdi/MINIPORT_WDI_RX_THROTTLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MINIPORT_WDI_RX_THROTTLE
---

# MINIPORT_WDI_RX_THROTTLE callback function


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The 
  MiniportWdiRxThrottle handler function  tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs.

This is a WDI miniport handler inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_THROTTLE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext [in]


TAL device handle returned by the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param RxThrottleLevel [in]


A <a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_rx_throttle_level">WDI_RX_THROTTLE_LEVEL</a> enumeration value that specifies the throttle level.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_rx_throttle_level">WDI_RX_THROTTLE_LEVEL</a>

