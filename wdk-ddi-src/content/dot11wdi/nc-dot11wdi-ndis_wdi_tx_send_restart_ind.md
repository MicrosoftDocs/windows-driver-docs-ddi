---
UID: NC:dot11wdi.NDIS_WDI_TX_SEND_RESTART_IND
title: NDIS_WDI_TX_SEND_RESTART_IND
author: windows-driver-content
description: The NdisWdiTxSendRestartIndication callback function resumes transmission on a given port to a given peer or peer-TID combination.
old-location: netvista\ndiswditxsendrestartindication.htm
old-project: netvista
ms.assetid: 40976CC1-89A4-420F-867F-99F857670DAE
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndiswditxsendrestartindication, NdisWdiTxSendRestartIndication callback function [Network Drivers Starting with Windows Vista], NdisWdiTxSendRestartIndication, NDIS_WDI_TX_SEND_RESTART_IND, NDIS_WDI_TX_SEND_RESTART_IND, dot11wdi/NdisWdiTxSendRestartIndication
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
-	NdisWdiTxSendRestartIndication
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_TX_SEND_RESTART_IND callback


## -description


The NdisWdiTxSendRestartIndication callback function resumes transmission on a given port to a given peer or peer-TID combination.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_TX_SEND_RESTART_IND NdisWdiTxSendRestartIndication;

VOID NdisWdiTxSendRestartIndication(
  _In_ NDIS_HANDLE         NdisMiniportDataPathHandle,
  _In_ WDI_PORT_ID         PortId,
  _In_ WDI_PEER_ID         PeerId,
  _In_ UINT32              ExTidBitmask,
  _In_ WDI_TX_PAUSE_REASON TxPauseReason
)
{ ... }
````


## -parameters




#### - NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


#### - PortId [in]

The port ID. Wildcards are accepted.


#### - PeerId [in]

The peer ID. Wildcards are accepted.


#### - ExTidBitmask [in]

The Extended TID bitmask. See <i>Remarks</i> section for more information.


### -param TxRestartReason






#### - TxPauseReason [in]

TX pause reason bitmask, specified as <a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a> value(s). See <i>Remarks</i> section for more information.


## -returns


This callback function does not return a value.



## -remarks


In the <i>ExTidBitmask</i> parameter, the <i>i</i><sup>th</sup> bit represents extended TID <i>i </i>(the least significant bit is bit 0) .

The <a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a> bitmask may contain a set of pause reasons. The pauses reasons are cumulative, so an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a> with a pause reason of <b>WDI_TX_PAUSE_REASON_CREDIT</b> followed by an <i>NdisWdiTxSendPauseIndication</i> with a pause reason of <b>WDI_TX_PAUSE_REASON_IHV1</b> requires an <i>NdisWdiTxSendRestartIndication</i> with a pause reason of (<b>WDI_TX_PAUSE_REASON_CREDIT</b> | <b>WDI_TX_PAUSE_REASON_IHV1</b>) for the set of queues to be unpaused.

If the pause reason is <b>WDI_TX_PAUSE_REASON_PS</b>, the TAL/target does not issue an <i>NdisWdiTxSendRestartIndication</i> to any of the affected queues until it has received an <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a> notification for that queue.
<i>NdisWdiTxSendRestartIndication</i> does not resume a queue if the queue has no remaining pause reason bits set after applying the restart reason bitmask.

If <b>TargetPriorityQueueing</b> is true, <a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a> must be a wildcard.  Only port or adapter restarts are allowed in this mode.



## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_target_capabilities.md">WDI_TXRX_CAPABILITIES</a>

<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_SEND_RESTART_IND callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

