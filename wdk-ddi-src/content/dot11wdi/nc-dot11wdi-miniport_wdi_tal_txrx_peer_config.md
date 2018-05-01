---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_PEER_CONFIG
title: MINIPORT_WDI_TAL_TXRX_PEER_CONFIG
author: windows-driver-content
description: The MiniportWdiTalTxRxPeerConfig handler function specifies the port ID, peer ID, and peer capabilities (for example, QoS capabilities). It is invoked after the peer has associated, which involves creation of the peer object in the TAL.
old-location: netvista\miniportwditaltxrxpeerconfig.htm
old-project: netvista
ms.assetid: 48BB554D-A19E-46C0-8278-690A686A731D
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_PEER_CONFIG, MINIPORT_WDI_TAL_TXRX_PEER_CONFIG callback, MiniportWdiTalTxRxPeerConfig, MiniportWdiTalTxRxPeerConfig callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxPeerConfig, netvista.miniportwditaltxrxpeerconfig
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
-	MiniportWdiTalTxRxPeerConfig
product: Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_PEER_CONFIG callback function


## -description


The 
  MiniportWdiTalTxRxPeerConfig handler function specifies the port ID, peer ID,  and peer capabilities  (for example, QoS capabilities). It is invoked after the peer has associated, which involves creation of the peer object in the TAL.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_PEER_CONFIG</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

Port ID associated with the peer.


### -param PeerId [in]

Peer ID for the peer.


### -param pPeerCfg [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn898190">WDI_TXRX_PEER_CFG</a> structure that contains negotiated QoS settings.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898190">WDI_TXRX_PEER_CFG</a>
 

 

