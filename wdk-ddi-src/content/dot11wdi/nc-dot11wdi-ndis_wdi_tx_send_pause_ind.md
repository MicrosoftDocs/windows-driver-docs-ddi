---
UID: NC:dot11wdi.NDIS_WDI_TX_SEND_PAUSE_IND
title: NDIS_WDI_TX_SEND_PAUSE_IND
author: windows-driver-content
description: The NdisWdiTxSendPauseIndication callback function pauses transmissions on a given port to a given peer or peer-TID combination.
old-location: netvista\ndiswditxsendpauseindication.htm
old-project: netvista
ms.assetid: A8001D08-36B8-4557-A763-103BDC807CA4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndiswditxsendpauseindication, NdisWdiTxSendPauseIndication callback function [Network Drivers Starting with Windows Vista], NdisWdiTxSendPauseIndication, NDIS_WDI_TX_SEND_PAUSE_IND, NDIS_WDI_TX_SEND_PAUSE_IND, dot11wdi/NdisWdiTxSendPauseIndication
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
-	NdisWdiTxSendPauseIndication
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---

# NDIS_WDI_TX_SEND_PAUSE_IND callback


## -description


The NdisWdiTxSendPauseIndication callback function pauses transmissions on a given port to a given peer or peer-TID combination.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_TX_SEND_PAUSE_IND NdisWdiTxSendPauseIndication;

VOID NdisWdiTxSendPauseIndication(
  _In_ NDIS_HANDLE         NdisMiniportDataPathHandle,
  _In_ WDI_PORT_ID         PortId,
  _In_ WDI_PEER_ID         PeerId,
  _In_ UINT32              ExTidBitmask,
  _In_ WDI_TX_PAUSE_REASON TxPauseReason
)
{ ... }
````


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID. Wildcards are accepted.


### -param PeerId [in]

The peer ID. Wildcards are accepted.


### -param ExTidBitmask [in]

The Extended TID bitmask. See <i>Remarks</i> section for more information.


### -param TxPauseReason [in]

TX pause reason bitmask, specified as <a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a> value(s). See <i>Remarks</i> section for more information.


## -returns



This callback function does not return a value.




## -remarks



In the <i>ExTidBitmask</i> parameter, the <i>i</i><sup>th</sup> bit represents extended TID <i>i </i>(the least significant bit is bit 0) .

The <a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a> bitmask may contain a set of pause reasons. The pauses reasons are cumulative, so an <i>NdisWdiTxSendPauseIndication</i> with a pause reason of <b>WDI_TX_PAUSE_REASON_CREDIT</b> followed by an <i>NdisWdiTxSendPauseIndication</i> with a pause reason of <b>WDI_TX_PAUSE_REASON_IHV1</b> requires an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_restart_ind.md">NdisWdiTxSendRestartIndication</a> with a pause reason of (<b>WDI_TX_PAUSE_REASON_CREDIT</b> | <b>WDI_TX_PAUSE_REASON_IHV1</b>) for the set of queues to be unpaused.

If the pause reason is <b>WDI_TX_PAUSE_REASON_PS</b>, the TAL/target does not issue an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_restart_ind.md">NdisWdiTxSendRestartIndication</a> to any of the affected queues until it has received an <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a> notification for that queue

If <b>TargetPriorityQueueing</b> is true, <a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a> must be a wildcard.  Only port or adapter pauses are allowed in this mode.




## -see-also

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_restart_ind.md">NdisWdiTxSendRestartIndication</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_SEND_PAUSE_IND callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

