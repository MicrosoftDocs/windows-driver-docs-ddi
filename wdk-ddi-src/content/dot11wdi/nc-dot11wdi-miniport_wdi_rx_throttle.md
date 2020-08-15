---
UID: NC:dot11wdi.MINIPORT_WDI_RX_THROTTLE
title: MINIPORT_WDI_RX_THROTTLE (dot11wdi.h)
description: The MiniportWdiRxThrottle handler function tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs.
old-location: netvista\miniportwdirxthrottle.htm
tech.root: netvista
ms.assetid: A5985C6D-3768-4ACE-B52B-3D3494334114
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_RX_THROTTLE callback function"]
ms.keywords: MINIPORT_WDI_RX_THROTTLE, MINIPORT_WDI_RX_THROTTLE callback, MiniportWdiRxThrottle, MiniportWdiRxThrottle callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxThrottle, netvista.miniportwdirxthrottle
f1_keywords:
 - "dot11wdi/MiniportWdiRxThrottle"
 - "MiniportWdiRxThrottle"
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
- UserDefined
api_location:
- dot11wdi.h
api_name:
- MiniportWdiRxThrottle
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_RX_THROTTLE callback function


## -description


The 
  MiniportWdiRxThrottle handler function  tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_THROTTLE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext 
[in]
TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param RxThrottleLevel 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_rx_throttle_level">WDI_RX_THROTTLE_LEVEL</a> enumeration value that specifies the throttle level.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_rx_throttle_level">WDI_RX_THROTTLE_LEVEL</a>
 

 

