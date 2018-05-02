---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM
title: MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM
author: windows-driver-content
description: The MiniportWdiTalTxRxPeerDeleteConfirm handler function is invoked after the completion of a PeerDeleteIndication call which did not return success.
old-location: netvista\miniportwditaltxrxpeerdeleteconfirm.htm
old-project: netvista
ms.assetid: 993C600F-E2FA-46D7-AE66-77048B481660
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM, MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM callback, MiniportWdiTalTxRxPeerDeleteConfirm, MiniportWdiTalTxRxPeerDeleteConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxPeerDeleteConfirm, netvista.miniportwditaltxrxpeerdeleteconfirm
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM callback function


## -description


The 
  MiniportWdiTalTxRxPeerDeleteConfirm handler function is invoked after the completion of a  <a href="https://msdn.microsoft.com/A13F2A98-BADA-43B8-A24B-0749C5558C35">PeerDeleteIndication</a> call which did not return success.  This is called after a successful <a href="https://msdn.microsoft.com/FA6BEAE9-5D48-463E-A398-518737D78867">MiniportWdiTxAbort</a> (or <a href="https://msdn.microsoft.com/1619BF14-DDEE-48CB-8E31-0CC17C8A4C6A">TxAbortConfirm</a>) and after all outstanding TX frames for the peer are completed.  After this call, the mapping between the peer Id and MAC address is no longer valid and the peer Id and MAC address may be used for future <a href="https://msdn.microsoft.com/58B60160-FE04-4EDE-900F-244D0F76E50D">PeerCreateIndication</a> calls.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_PEER_DELETE_CONFIRM</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

Port ID associated with the peer.


### -param PeerId [in]

Peer ID for the peer.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/FA6BEAE9-5D48-463E-A398-518737D78867">MiniportWdiTxAbort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/58B60160-FE04-4EDE-900F-244D0F76E50D">PeerCreateIndication</a>



<a href="https://msdn.microsoft.com/A13F2A98-BADA-43B8-A24B-0749C5558C35">PeerDeleteIndication</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/1619BF14-DDEE-48CB-8E31-0CC17C8A4C6A">TxAbortConfirm</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
 

 

