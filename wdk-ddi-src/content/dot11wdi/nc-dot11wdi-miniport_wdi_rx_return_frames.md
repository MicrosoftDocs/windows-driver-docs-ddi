---
UID: NC:dot11wdi.MINIPORT_WDI_RX_RETURN_FRAMES
title: MINIPORT_WDI_RX_RETURN_FRAMES (dot11wdi.h)
description: The MiniportWdiRxReturnFrames handler function returns a NET_BUFFER_LIST structure (and associated data buffers) to the TAL.
old-location: netvista\miniportwdirxreturnframes.htm
tech.root: netvista
ms.assetid: BF2DB7C6-97F9-454B-8DED-E8CC21A4F07F
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_RX_RETURN_FRAMES, MINIPORT_WDI_RX_RETURN_FRAMES callback, MiniportWdiRxReturnFrames, MiniportWdiRxReturnFrames callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxReturnFrames, netvista.miniportwdirxreturnframes
f1_keywords:
 - "dot11wdi/MiniportWdiRxReturnFrames"
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
- MiniportWdiRxReturnFrames
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_RX_RETURN_FRAMES callback function


## -description


The 
  MiniportWdiRxReturnFrames handler function returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure (and associated data buffers) to the TAL.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_RETURN_FRAMES</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param pNBL [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> chain being returned to the IHV miniport.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>
 

 

