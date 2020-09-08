---
UID: NC:dot11wdi.MINIPORT_WDI_RX_PPDU_RSSI
title: MINIPORT_WDI_RX_PPDU_RSSI (dot11wdi.h)
description: The MiniportWdiRxPpduRssi handler function returns the absolute value of RSSI (in dB) for the PPDU. The RxMgr may request the RSSI only once per data indication using the PNET_BUFFER_LIST obtained from MiniportWdiRxGetMpdus.
old-location: netvista\miniportwdirxppdurssi.htm
tech.root: netvista
ms.assetid: 34C34C42-E5E1-44F6-AC81-ADC77206DED0
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_RX_PPDU_RSSI callback function"]
ms.keywords: MINIPORT_WDI_RX_PPDU_RSSI, MINIPORT_WDI_RX_PPDU_RSSI callback, MiniportWdiRxPpduRssi, MiniportWdiRxPpduRssi callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxPpduRssi, netvista.miniportwdirxppdurssi
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
 - MINIPORT_WDI_RX_PPDU_RSSI
 - dot11wdi/MINIPORT_WDI_RX_PPDU_RSSI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiRxPpduRssi
---

# MINIPORT_WDI_RX_PPDU_RSSI callback function


## -description

The 
  MiniportWdiRxPpduRssi handler function returns the absolute value of RSSI (in dB) for the PPDU. The RxMgr may request the RSSI only once per data indication using the PNET_BUFFER_LIST obtained from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_rx_get_mpdus">MiniportWdiRxGetMpdus</a>.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_PPDU_RSSI</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param pNBL 

[in]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> for which the RSSI is requested.

### -param pRssi 

[out]
The absolute value of RSSI, in dB.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>

