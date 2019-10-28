---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_DEINITIALIZE
title: MINIPORT_WDI_TAL_TXRX_DEINITIALIZE (dot11wdi.h)
description: The MiniportWdiTalTxRxDeinitialize handler function is invoked in the context of miniport halt. The functional components RXEngine and TxEngine have already been stopped and any pending data frames completed/returned.
old-location: netvista\miniportwditaltxrxdeinitialize.htm
tech.root: netvista
ms.assetid: E8A77709-7E35-4FFC-B7EC-19E5256AB55F
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_DEINITIALIZE, MINIPORT_WDI_TAL_TXRX_DEINITIALIZE callback, MiniportWdiTalTxRxDeinitialize, MiniportWdiTalTxRxDeinitialize callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxDeinitialize, netvista.miniportwditaltxrxdeinitialize
ms.topic: callback
f1_keywords:
 - "dot11wdi/MiniportWdiTalTxRxDeinitialize"
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
- MiniportWdiTalTxRxDeinitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_DEINITIALIZE callback function


## -description


The 
  MiniportWdiTalTxRxDeinitialize handler function is invoked in the context of miniport halt. The functional components RXEngine and TxEngine have already been stopped and any pending data frames completed/returned.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_DEINITIALIZE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>
 

 

