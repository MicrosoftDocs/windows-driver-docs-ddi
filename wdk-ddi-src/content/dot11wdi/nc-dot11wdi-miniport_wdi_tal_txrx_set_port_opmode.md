---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE
title: MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE (dot11wdi.h)
description: The MiniportWdiTalTxRxSetPortOpMode handler function specifies the opmode used for the port so that the TxEngine and RxEngine enable the corresponding functionality.
old-location: netvista\miniportwditaltxrxsetportopmode.htm
tech.root: netvista
ms.assetid: 86F3005E-8BB3-4309-AFDE-7FA6E0427BFD
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE callback function"]
ms.keywords: MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE, MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE callback, MiniportWdiTalTxRxSetPortOpMode, MiniportWdiTalTxRxSetPortOpMode callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxSetPortOpMode, netvista.miniportwditaltxrxsetportopmode
f1_keywords:
 - "dot11wdi/MiniportWdiTalTxRxSetPortOpMode"
 - "MiniportWdiTalTxRxSetPortOpMode"
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
- MiniportWdiTalTxRxSetPortOpMode
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE callback function


## -description


The 
  MiniportWdiTalTxRxSetPortOpMode handler function specifies the opmode used for the port so that the TxEngine and RxEngine enable the corresponding functionality. It is called after the set-opmode command has been completed on the control path, but before a BSS is created (connect or start GO).

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext 
[in]
TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


### -param PortId 
[in]
Port ID for the port.


### -param Opmode 
[in]

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_operation_mode">WDI_OPERATION_MODE</a> value that specifies the operation mode for the port.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-general-datapath-interfaces">WDI general datapath interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_operation_mode">WDI_OPERATION_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>
 

 

