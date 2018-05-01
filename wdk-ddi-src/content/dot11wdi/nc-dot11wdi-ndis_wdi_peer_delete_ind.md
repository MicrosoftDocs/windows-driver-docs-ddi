---
UID: NC:dot11wdi.NDIS_WDI_PEER_DELETE_IND
title: NDIS_WDI_PEER_DELETE_IND
author: windows-driver-content
description: The NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address.
old-location: netvista\ndiswdipeerdeleteindication.htm
old-project: netvista
ms.assetid: A13F2A98-BADA-43B8-A24B-0749C5558C35
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDIS_WDI_PEER_DELETE_IND, NDIS_WDI_PEER_DELETE_IND callback, NdisWdiPeerDeleteIndication, NdisWdiPeerDeleteIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiPeerDeleteIndication, netvista.ndiswdipeerdeleteindication
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
-	NdisWdiPeerDeleteIndication
product: Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_PEER_DELETE_IND callback function


## -description


The 
  NdisWdiPeerDeleteIndication callback function initiates the removal of the association of between a peer ID and a peer MAC address. Once this indication is processed, the peer ID can no longer be used  in subsequent Rx indications and the IHV may not inject any Tx frames for this peer.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID.


### -param PeerId [in]

The peer ID.


### -param *pWifiStatus [out]

Indicates whether the peer deletion completed synchronously (if status is set to <b>NDIS_STATUS_SUCCESS</b>), or whether WDI will issue a <a href="https://msdn.microsoft.com/993C600F-E2FA-46D7-AE66-77048B481660">MiniportWdiTalTxRxPeerDeleteConfirm</a> when peer deletion completes.


## -returns



This callback function does not return a value.




## -remarks



In PeerQueueing mode, the TxMgr issues a TxAbort for the peer.  If the <a href="https://msdn.microsoft.com/FA6BEAE9-5D48-463E-A398-518737D78867">MiniportWdiTxAbort</a> completes synchronously and there are no outstanding TX frames for that peer, WDI_STATUS is set to NDIS_STATUS_SUCCESS and the peer deletion is complete (see <a href="https://msdn.microsoft.com/993C600F-E2FA-46D7-AE66-77048B481660">MiniportWdiTalTxRxPeerDeleteConfirm</a> for  the description of a peer delete completion).  Otherwise, WDI issues a <i>MiniportWdiTalTxRxPeerDeleteConfirm</i> when the TxAbort is completed and there are no outstanding frames for this peer.




## -see-also




<a href="https://msdn.microsoft.com/993C600F-E2FA-46D7-AE66-77048B481660">MiniportWdiTalTxRxPeerDeleteConfirm</a>



<a href="https://msdn.microsoft.com/FA6BEAE9-5D48-463E-A398-518737D78867">MiniportWdiTxAbort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
 

 

