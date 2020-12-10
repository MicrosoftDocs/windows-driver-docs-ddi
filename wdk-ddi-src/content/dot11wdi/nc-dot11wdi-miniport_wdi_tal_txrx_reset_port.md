---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_RESET_PORT
title: MINIPORT_WDI_TAL_TXRX_RESET_PORT (dot11wdi.h)
description: The MiniportWdiTalTxRxResetPort handler function is invoked before a dot11 reset task is issued to the target.
old-location: netvista\miniportwditaltxrxresetport.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_TAL_TXRX_RESET_PORT callback function"]
ms.keywords: MINIPORT_WDI_TAL_TXRX_RESET_PORT, MINIPORT_WDI_TAL_TXRX_RESET_PORT callback, MiniportWdiTalTxRxResetPort, MiniportWdiTalTxRxResetPort callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxResetPort, netvista.miniportwditaltxrxresetport
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
 - MINIPORT_WDI_TAL_TXRX_RESET_PORT
 - dot11wdi/MINIPORT_WDI_TAL_TXRX_RESET_PORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiTalTxRxResetPort
---

# MINIPORT_WDI_TAL_TXRX_RESET_PORT callback function


## -description

The 
  MiniportWdiTalTxRxResetPort handler function is invoked before a dot11 reset task is issued to the target.  The functional components RXEngine/TxEngine have already stopped operations associated with this port and any pending data frames have been completed/returned. It allows the TX/RX components to clear  the port state. This does not involve changing the operation mode.

This is a WDI miniport handler inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_RESET_PORT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
Port ID for the port being reset.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>



<a href="/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>
