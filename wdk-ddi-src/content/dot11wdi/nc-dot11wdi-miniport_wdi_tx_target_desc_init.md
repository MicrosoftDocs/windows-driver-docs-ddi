---
UID: NC:dot11wdi.MINIPORT_WDI_TX_TARGET_DESC_INIT
title: MINIPORT_WDI_TX_TARGET_DESC_INIT
author: windows-driver-content
description: The MINIPORT_WDI_TX_TARGET_DESC_INIT callback function associates an opaque target TX descriptor with the NET_BUFFER_LIST (MiniportReserved[1] field) and (if applicable) populates the TX cost field (in credit units) in the WDI_FRAME_METADATA buffer of the NET_BUFFER_LIST (MiniportReserved[0]).
old-location: netvista\miniportwditxtargetdescinit.htm
old-project: netvista
ms.assetid: EAFE6F7D-6820-4626-863D-C28FBFFCE6A0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwditxtargetdescinit, MiniportWdiTxTargetDescInit callback function [Network Drivers Starting with Windows Vista], MiniportWdiTxTargetDescInit, MINIPORT_WDI_TX_TARGET_DESC_INIT, MINIPORT_WDI_TX_TARGET_DESC_INIT, dot11wdi/MiniportWdiTxTargetDescInit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	MiniportWdiTxTargetDescInit
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_TX_TARGET_DESC_INIT callback


## -description


The 
  <i>MINIPORT_WDI_TX_TARGET_DESC_INIT</i> callback function associates an opaque target TX descriptor with the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> (<b>MiniportReserved[1]</b> field) and (if applicable) populates the TX cost field (in credit units) in the <a href="..\dot11wdi\ns-dot11wdi-_wdi_frame_metadata.md">WDI_FRAME_METADATA</a> buffer of the <b>NET_BUFFER_LIST</b> (<b>MiniportReserved[0]</b>).

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_TARGET_DESC_INIT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_TX_TARGET_DESC_INIT MiniportWdiTxTargetDescInit;

VOID MiniportWdiTxTargetDescInit(
  _In_  TAL_TXRX_HANDLE  MiniportTalTxRxContext,
  _In_  PNET_BUFFER_LIST pNBL,
  _Out_ NDIS_STATUS      *pWifiStatus
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MINIPORT_WDI_TAL_TXRX_INITIALIZE</a> callback function.


### -param pNBL [in]

Pointer to a single <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>.


### -param *pWifiStatus [out]

Pointer to the status set by the IHV to indicate the result of the <i>MINIPORT_WDI_TX_TARGET_DESC_INIT</i> callback function.


## -returns


This callback function does not return a value.



## -remarks


A status of <b>NDIS_STATUS_RESOURCES</b> must only be used when Tx descriptors are exhausted.  The best behavior occurs if the IHV miniport does not use <b>NDIS_STATUS_RESOURCES</b>.  Any status other than <b>NDIS_STATUS_SUCCESS</b> and <b>NDIS_STATUS_RESOURCES</b> must be used for any other error that indicates the IHV miniport or firmware is unable to process the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>.

The IHV miniport may utilize the backfill in the <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> by using the appropriate NDIS retreat and advance functions.  The start of the packet offset must be restored before or in the <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_target_desc_deinit.md">MINIPORT_WDI_TX_TARGET_DESC_DEINIT</a> callback function.  The TxMgr determines the frame length during dequeue time so any change to the frame length in the <i>MINIPORT_WDI_TX_TARGET_DESC_INIT</i> callback function is included in limiting the dequeue size to the quantum.  In this case, the IHV miniport should appropriately adjust the quantum to account for the delta.
<div class="alert"><b>Important</b>  The IHV miniport is not permitted to make any indication in the context of this call.
The TxMgr serializes calls to <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">TxTargetDescInitHandler</a>.</div><div> </div>


## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_wdi_frame_metadata.md">WDI_FRAME_METADATA</a>

<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_target_desc_deinit.md">MINIPORT_WDI_TX_TARGET_DESC_DEINIT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TX_TARGET_DESC_INIT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

