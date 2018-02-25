---
UID: NC:dot11wdi.NDIS_WDI_TX_INJECT_FRAME_IND
title: NDIS_WDI_TX_INJECT_FRAME_IND
author: windows-driver-content
description: The NdisWdiTxInjectFrameIndication callback function allows the LE to inject frames through the regular datapath (for example, authentication/association requests/responses, Wi-Fi Direct action frames).
old-location: netvista\ndiswditxinjectframeindication.htm
old-project: netvista
ms.assetid: C384FAFF-E22D-4FA2-8B11-F6C046003C70
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_WDI_TX_INJECT_FRAME_IND, NdisWdiTxInjectFrameIndication, NdisWdiTxInjectFrameIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxInjectFrameIndication, netvista.ndiswditxinjectframeindication
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
-	NdisWdiTxInjectFrameIndication
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_TX_INJECT_FRAME_IND callback


## -description


The NdisWdiTxInjectFrameIndication callback function allows the LE to inject frames through the regular datapath (for example, authentication/association requests/responses, Wi-Fi Direct action frames).

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_TX_INJECT_FRAME_IND NdisWdiTxInjectFrameIndication;

VOID NdisWdiTxInjectFrameIndication(
  _In_ NDIS_HANDLE               NdisMiniportDataPathHandle,
  _In_ WDI_PORT_ID               PortId,
  _In_ WDI_PEER_ID               PeerId,
  _In_ WDI_EXTENDED_TID          ExTid,
  _In_ PNET_BUFFER_LIST          pNBL,
  _In_ BOOLEAN                   bIsUnicast,
  _In_ BOOLEAN                   bUseLegacyRates,
  _In_ UINT16                    Ethertype,
  _In_ WDI_EXEMPTION_ACTION_TYPE ExemptionAction
)
{ ... }
````


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID. 


### -param PeerId [in]

The peer ID. When <b>TargetPriorityQueueing</b> is true, this must be set to the wildcard value.


### -param ExTid [in]

The extended TID.


### -param pNBL [in]

Pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain.


### -param bIsUnicast [in]

Specifies if the frames are to a unicast receiver address.


### -param bUseLegacyRates [in]

Specifies if legacy rates should be used to send the frames.


### -param Ethertype [in]

Specifies the Ethertype of the frames.


### -param ExemptionAction [in]

Specifies the ExemptionAction of the frames.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_exemption_action_type.md">WDI_EXEMPTION_ACTION_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_INJECT_FRAME_IND callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

