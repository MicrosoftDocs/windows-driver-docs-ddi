---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_PEER_CONFIG
title: MINIPORT_WDI_TAL_TXRX_PEER_CONFIG
author: windows-driver-content
description: The MiniportWdiTalTxRxPeerConfig handler function specifies the port ID, peer ID, and peer capabilities (for example, QoS capabilities). It is invoked after the peer has associated, which involves creation of the peer object in the TAL.
old-location: netvista\miniportwditaltxrxpeerconfig.htm
old-project: netvista
ms.assetid: 48BB554D-A19E-46C0-8278-690A686A731D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_PEER_CONFIG, MiniportWdiTalTxRxPeerConfig, MiniportWdiTalTxRxPeerConfig callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxPeerConfig, netvista.miniportwditaltxrxpeerconfig
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
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_TAL_TXRX_PEER_CONFIG callback


## -description


The 
  MiniportWdiTalTxRxPeerConfig handler function specifies the port ID, peer ID,  and peer capabilities  (for example, QoS capabilities). It is invoked after the peer has associated, which involves creation of the peer object in the TAL.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_PEER_CONFIG</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_TAL_TXRX_PEER_CONFIG MiniportWdiTalTxRxPeerConfig;

VOID MiniportWdiTalTxRxPeerConfig(
  _In_ TAL_TXRX_HANDLE    MiniportTalTxRxContext,
  _In_ WDI_PORT_ID        PortId,
  _In_ WDI_PEER_ID        PeerId,
  _In_ PWDI_TXRX_PEER_CFG pPeerCfg
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


### -param pPeerCfg [in]

Pointer to a <a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_peer_cfg.md">WDI_TXRX_PEER_CFG</a> structure that contains negotiated QoS settings.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_peer_cfg.md">WDI_TXRX_PEER_CFG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TAL_TXRX_PEER_CONFIG callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

