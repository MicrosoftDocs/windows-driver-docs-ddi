---
UID: NC:dot11wdi.MINIPORT_WDI_RX_STOP
title: MINIPORT_WDI_RX_STOP (dot11wdi.h)
description: The MiniportWdiRxStop handler function stops RX on a given port and accepts the wildcard port ID to stop RX across the adapter.
old-location: netvista\miniportwdirxstop.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_RX_STOP callback function"]
ms.keywords: MINIPORT_WDI_RX_STOP, MINIPORT_WDI_RX_STOP callback, MiniportWdiRxStop, MiniportWdiRxStop callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxStop, netvista.miniportwdirxstop
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
 - MINIPORT_WDI_RX_STOP
 - dot11wdi/MINIPORT_WDI_RX_STOP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MINIPORT_WDI_RX_STOP
---

# MINIPORT_WDI_RX_STOP callback function


## -description

The 
  MiniportWdiRxStop handler function stops RX on a given port and accepts the wildcard port ID  to stop RX across the adapter. The TAL completes the RX stop operation by completing the request with a success status, or by completing it with a pending status and asynchronously indicating <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_rx_stop_confirm">RxStopConfirm</a>.

This is a WDI miniport handler inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.

Prior to completing the indication, the target must be configured to stop indicating new traffic on the selected port or the entire adapter.

This request is issued to the TAL as part of a transition to low power (adapter) and dot11 reset (port).
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_STOP</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
The port ID.

### -param pWifiStatus 

[out]
Status from the IHV miniport. A success status indicates that the operation completion synchronously.  A pending status indicates that the stop will be asynchronously confirmed.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>



<a href="/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>

