---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM
title: MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM
author: windows-driver-content
description: The MiniportWdiTalTxRxPeerDeleteConfirm handler function is invoked after the completion of a PeerDeleteIndication call which did not return success.
old-location: netvista\miniportwditaltxrxpeerdeleteconfirm.htm
old-project: netvista
ms.assetid: 993C600F-E2FA-46D7-AE66-77048B481660
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM, MiniportWdiTalTxRxPeerDeleteConfirm, MiniportWdiTalTxRxPeerDeleteConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxPeerDeleteConfirm, netvista.miniportwditaltxrxpeerdeleteconfirm
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	MiniportWdiTalTxRxPeerDeleteConfirm
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM callback


## -description


The 
  MiniportWdiTalTxRxPeerDeleteConfirm handler function is invoked after the completion of a  <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_peer_delete_ind.md">PeerDeleteIndication</a> call which did not return success.  This is called after a successful <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a> (or <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_abort_confirm.md">TxAbortConfirm</a>) and after all outstanding TX frames for the peer are completed.  After this call, the mapping between the peer Id and MAC address is no longer valid and the peer Id and MAC address may be used for future <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_peer_create_ind.md">PeerCreateIndication</a> calls.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM MiniportWdiTalTxRxPeerDeleteConfirm;

VOID MiniportWdiTalTxRxPeerDeleteConfirm(
  _In_ TAL_TXRX_HANDLE MiniportTalTxRxContext,
  _In_ WDI_PORT_ID     PortId,
  _In_ WDI_PEER_ID     PeerId
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

Port ID associated with the peer.


### -param PeerId [in]

Peer ID for the peer.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_peer_create_ind.md">PeerCreateIndication</a>



<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a>



<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_peer_delete_ind.md">PeerDeleteIndication</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_abort_confirm.md">TxAbortConfirm</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

