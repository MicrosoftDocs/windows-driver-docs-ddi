---
UID: NC:dot11wdi.MINIPORT_WDI_TX_TAL_SEND_COMPLETE
title: MINIPORT_WDI_TX_TAL_SEND_COMPLETE (dot11wdi.h)
description: The MiniportWdiTxTalSendComplete handler function returns ownership of one or more TX frame injected by the TAL back to the TxEngine.
old-location: netvista\miniportwditxtalsendcomplete.htm
tech.root: netvista
ms.assetid: 347B069F-76B6-42D5-9613-7D0214C2FEDB
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_TX_TAL_SEND_COMPLETE, MINIPORT_WDI_TX_TAL_SEND_COMPLETE callback, MiniportWdiTxTalSendComplete, MiniportWdiTxTalSendComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxTalSendComplete, netvista.miniportwditxtalsendcomplete
ms.topic: callback
f1_keywords:
 - "dot11wdi/MiniportWdiTxTalSendComplete"
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
- MiniportWdiTxTalSendComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TX_TAL_SEND_COMPLETE callback function


## -description


The 
  MiniportWdiTxTalSendComplete handler function returns ownership of one or more TX frame injected by the TAL back to the TxEngine. The TxMgr uses this interface to return a frame after receiving the corresponding transfer and TX completion (if applicable). Frames completed with different frame statuses are returned in separate requests.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_TAL_SEND_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param pNBL [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> chain.


### -param TxFrameStatus [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_frame_status">WDI_TX_FRAME_STATUS</a> enumeration value that specifies the TX frame status.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-tx-path">WDI TX path</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_frame_status">WDI_TX_FRAME_STATUS</a>
 

 

