---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_STOP
title: MINIPORT_WDI_TAL_TXRX_STOP (dot11wdi.h)
description: The MiniportWdiTalTxRxStop handler function stops TXRX communication between the TAL and the target.
old-location: netvista\miniportwditaltxrxstop.htm
tech.root: netvista
ms.assetid: 21841DC6-B95F-4372-BBD1-EA195832A118
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_TAL_TXRX_STOP callback function"]
ms.keywords: MINIPORT_WDI_TAL_TXRX_STOP, MINIPORT_WDI_TAL_TXRX_STOP callback, MiniportWdiTalTxRxStop, MiniportWdiTalTxRxStop callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxStop, netvista.miniportwditaltxrxstop
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
 - MINIPORT_WDI_TAL_TXRX_STOP
 - dot11wdi/MINIPORT_WDI_TAL_TXRX_STOP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiTalTxRxStop
---

# MINIPORT_WDI_TAL_TXRX_STOP callback function


## -description

The 
  MiniportWdiTalTxRxStop handler function stops TXRX communication between the TAL and the target.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_STOP</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>

