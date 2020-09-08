---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_ADD_PORT
title: MINIPORT_WDI_TAL_TXRX_ADD_PORT (dot11wdi.h)
description: The MiniportWdiTalTxRxAddPort handler function notifies the datapath components of the creation of a new virtual port.
old-location: netvista\miniportwditaltxrxaddport.htm
tech.root: netvista
ms.assetid: D3006A0B-B0E0-4FEA-864A-FA4B75594FB0
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_TAL_TXRX_ADD_PORT callback function"]
ms.keywords: MINIPORT_WDI_TAL_TXRX_ADD_PORT, MINIPORT_WDI_TAL_TXRX_ADD_PORT callback, MiniportWdiTalTxRxAddPort, MiniportWdiTalTxRxAddPort callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxAddPort, netvista.miniportwditaltxrxaddport
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
 - MINIPORT_WDI_TAL_TXRX_ADD_PORT
 - dot11wdi/MINIPORT_WDI_TAL_TXRX_ADD_PORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiTalTxRxAddPort
---

# MINIPORT_WDI_TAL_TXRX_ADD_PORT callback function


## -description

The 
  MiniportWdiTalTxRxAddPort handler function notifies the datapath components of the creation of a new virtual port. It is invoked after the completion of the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wdi-task-create-port">OID_WDI_TASK_CREATE_PORT</a> command and specifies the PortID designated by the target for the port.

It also specifies the default operation mode for the port.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_ADD_PORT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext 

[in]
TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
Port ID designated by the target for the port.

### -param OpMode 

[in]
Default operation mode for the port.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wdi-task-create-port">OID_WDI_TASK_CREATE_PORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_operation_mode">WDI_OPERATION_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>

