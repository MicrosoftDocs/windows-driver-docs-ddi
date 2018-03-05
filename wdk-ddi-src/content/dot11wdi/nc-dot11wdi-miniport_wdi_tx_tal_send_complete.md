---
UID: NC:dot11wdi.MINIPORT_WDI_TX_TAL_SEND_COMPLETE
title: MINIPORT_WDI_TX_TAL_SEND_COMPLETE
author: windows-driver-content
description: The MiniportWdiTxTalSendComplete handler function returns ownership of one or more TX frame injected by the TAL back to the TxEngine.
old-location: netvista\miniportwditxtalsendcomplete.htm
old-project: netvista
ms.assetid: 347B069F-76B6-42D5-9613-7D0214C2FEDB
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MINIPORT_WDI_TX_TAL_SEND_COMPLETE, MiniportWdiTxTalSendComplete, MiniportWdiTxTalSendComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTxTalSendComplete, netvista.miniportwditxtalsendcomplete
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
-	MiniportWdiTxTalSendComplete
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_TX_TAL_SEND_COMPLETE callback


## -description


The 
  MiniportWdiTxTalSendComplete handler function returns ownership of one or more TX frame injected by the TAL back to the TxEngine. The TxMgr uses this interface to return a frame after receiving the corresponding transfer and TX completion (if applicable). Frames completed with different frame statuses are returned in separate requests.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_TAL_SEND_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_TX_TAL_SEND_COMPLETE MiniportWdiTxTalSendComplete;

VOID MiniportWdiTxTalSendComplete(
  _In_ TAL_TXRX_HANDLE     MiniportTalTxRxContext,
  _In_ PNET_BUFFER_LIST    pNBL,
  _In_ WDI_TX_FRAME_STATUS TxFrameStatus
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param pNBL [in]

Pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain.


### -param TxFrameStatus [in]

A <a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_frame_status.md">WDI_TX_FRAME_STATUS</a> enumeration value that specifies the TX frame status.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_frame_status.md">WDI_TX_FRAME_STATUS</a>



<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TX_TAL_SEND_COMPLETE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

