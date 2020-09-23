---
UID: NC:dot11wdi.NDIS_WDI_TX_INJECT_FRAME_IND
title: NDIS_WDI_TX_INJECT_FRAME_IND (dot11wdi.h)
description: The NdisWdiTxInjectFrameIndication callback function allows the LE to inject frames through the regular datapath (for example, authentication/association requests/responses, Wi-Fi Direct action frames).
old-location: netvista\ndiswditxinjectframeindication.htm
tech.root: netvista
ms.assetid: C384FAFF-E22D-4FA2-8B11-F6C046003C70
ms.date: 05/02/2018
keywords: ["NDIS_WDI_TX_INJECT_FRAME_IND callback function"]
ms.keywords: NDIS_WDI_TX_INJECT_FRAME_IND, NDIS_WDI_TX_INJECT_FRAME_IND callback, NdisWdiTxInjectFrameIndication, NdisWdiTxInjectFrameIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxInjectFrameIndication, netvista.ndiswditxinjectframeindication
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
 - NDIS_WDI_TX_INJECT_FRAME_IND
 - dot11wdi/NDIS_WDI_TX_INJECT_FRAME_IND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - NdisWdiTxInjectFrameIndication
---

# NDIS_WDI_TX_INJECT_FRAME_IND callback function


## -description

The NdisWdiTxInjectFrameIndication callback function allows the LE to inject frames through the regular datapath (for example, authentication/association requests/responses, Wi-Fi Direct action frames).

This is a callback inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.

## -parameters

### -param NdisMiniportDataPathHandle 

[in]
The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId 

[in]
The port ID.

### -param PeerId 

[in]
The peer ID. When <b>TargetPriorityQueueing</b> is true, this must be set to the wildcard value.

### -param ExTid 

[in]
The extended TID.

### -param pNBL 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> chain.

### -param bIsUnicast 

[in]
Specifies if the frames are to a unicast receiver address.

### -param bUseLegacyRates 

[in]
Specifies if legacy rates should be used to send the frames.

### -param Ethertype 

[in]
Specifies the Ethertype of the frames.

### -param ExemptionAction 

[in]
Specifies the ExemptionAction of the frames.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_exemption_action_type">WDI_EXEMPTION_ACTION_TYPE</a>



<a href="/windows-hardware/drivers/network/wdi-extended-tid">WDI_EXTENDED_TID</a>



<a href="/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>