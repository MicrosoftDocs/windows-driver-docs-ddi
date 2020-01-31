---
UID: NC:dot11wdi.NDIS_WDI_RX_STOP_CONFIRM
title: NDIS_WDI_RX_STOP_CONFIRM (dot11wdi.h)
description: The NdisWdiRxStopConfirm callback function indicates completion of a MiniportWdiRxStop request.
old-location: netvista\ndiswdirxstopconfirm.htm
tech.root: netvista
ms.assetid: 2022915A-2717-4098-BCD8-34130A161967
ms.date: 05/02/2018
ms.keywords: NDIS_WDI_RX_STOP_CONFIRM, NDIS_WDI_RX_STOP_CONFIRM callback, NdisWdiRxStopConfirm, NdisWdiRxStopConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiRxStopConfirm, netvista.ndiswdirxstopconfirm
f1_keywords:
 - "dot11wdi/NdisWdiRxStopConfirm"
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
- NdisWdiRxStopConfirm
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_RX_STOP_CONFIRM callback function


## -description


The 
  NdisWdiRxStopConfirm callback function indicates completion of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_rx_stop">MiniportWdiRxStop</a> request.  If traffic is stopped across the entire adapter, the target must stop indicating frames that match the stop request to the host prior to issuing  <b>NdisWdiRxStopConfirm</b>.

This is a callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_rx_stop">MiniportWdiRxStop</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>
 

 

