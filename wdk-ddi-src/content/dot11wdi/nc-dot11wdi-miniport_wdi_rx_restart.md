---
UID: NC:dot11wdi.MINIPORT_WDI_RX_RESTART
title: MINIPORT_WDI_RX_RESTART (dot11wdi.h)
description: The MiniportWdiRxRestart handler function configures the RxEngine to restart indicating data traffic. This is issued following a MiniportWdiRxStop.
old-location: netvista\miniportwdirxrestart.htm
tech.root: netvista
ms.assetid: 465716C7-A157-4B06-BAE2-F18A08126040
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_RX_RESTART callback function"]
ms.keywords: MINIPORT_WDI_RX_RESTART, MINIPORT_WDI_RX_RESTART callback, MiniportWdiRxRestart, MiniportWdiRxRestart callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxRestart, netvista.miniportwdirxrestart
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
 - MINIPORT_WDI_RX_RESTART
 - dot11wdi/MINIPORT_WDI_RX_RESTART
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiRxRestart
---

# MINIPORT_WDI_RX_RESTART callback function


## -description

The 
  MiniportWdiRxRestart handler function configures the RxEngine to restart indicating data traffic. This is issued following a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_rx_stop">MiniportWdiRxStop</a>.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_RESTART</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
The port ID.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>

