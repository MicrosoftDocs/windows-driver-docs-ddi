---
UID: NC:dot11wdi.MINIPORT_WDI_TX_ABORT
title: MINIPORT_WDI_TX_ABORT (dot11wdi.h)
description: The MiniportWdiTxAbort handler function aborts outstanding TX frames for a given port or peer, which includes initiating the completion of frames owned by the TAL/target.
old-location: netvista\miniportwditxabort.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_TX_ABORT callback function"]
ms.keywords: MINIPORT_WDI_TX_ABORT, MINIPORT_WDI_TX_ABORT callback, MiniportWdiTxAbort, MiniportWdiTxAbort callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxAbort, netvista.miniportwditxabort
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
 - MINIPORT_WDI_TX_ABORT
 - dot11wdi/MINIPORT_WDI_TX_ABORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MINIPORT_WDI_TX_ABORT
---

# MINIPORT_WDI_TX_ABORT callback function


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The 
  MiniportWdiTxAbort handler function aborts outstanding TX frames for a given port or peer, which includes initiating the completion of frames owned by the TAL/target. This request is issued to the TAL as part of handling <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> (adapter-wide TX abort), dot11 reset (port-wide abort), and after <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_peer_delete_ind">NdisWdiPeerDeleteIndication</a> if WDI is operating in peer queuing mode.

This is a WDI miniport handler inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_ABORT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportTalTxRxContext [in]


TAL device handle returned by the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId [in]


The port ID.

### -param PeerId [in]


The peer ID.

### -param pWifiStatus [out]


Pointer to a status of the MiniportWdiTxAbort, which should be set by the IHV miniport.  See the <i>Remarks</i> section for more information.

## -remarks

A wildcard may be specified for the <i>PeerId</i> to stop TX on a port.

A wildcard for <i>PortId</i> and <i>PeerId</i> may be specified to stop TX across the adapter.

To complete the stop operation, the TAL must do the following steps.

<ol>
<li>Initiate the return of ownership of TX data buffers corresponding to the input parameters to the host. These frames should be completed by indicating transfer completion for all frames passed to the TxEngine in send requests and indicating <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_complete_ind">NdisWdiTxSendCompleteIndication</a> for outstanding TX frames that require explicit send completion (if the TX frame was not transfer completed with a success code).</li>
<li>Return a success status, or return a pending status and issue <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_abort_confirm">NdisWdiTxAbortConfirm</a> later.</li>
</ol>

#### Examples

To define a MiniportWdiTxAbort function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiTxAbort function that is named "MyTxAbort", use the <b>MINIPORT_WDI_TX_ABORT</b> type as shown in this code example:


```
MINIPORT_WDI_TX_ABORT MyTxAbort;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyTxAbort(
    TAL_TXRX_HANDLE MiniportTalTxRxContext,
    WDI_PORT_ID PortId,
    WDI_PEER_ID PeerId,
    NDIS_STATUS *pWifiStatus
    )
  {...}
```

The <b>MINIPORT_WDI_TX_ABORT</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_TX_ABORT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_peer_delete_ind">NdisWdiPeerDeleteIndication</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_abort_confirm">NdisWdiTxAbortConfirm</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_complete_ind">NdisWdiTxSendCompleteIndication</a>



<a href="/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="/windows-hardware/drivers/network/wdi-tx-path">WDI TX path</a>



<a href="/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>

