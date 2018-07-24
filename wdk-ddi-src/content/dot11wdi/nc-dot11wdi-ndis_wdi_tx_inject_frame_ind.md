---
UID: NC:dot11wdi.NDIS_WDI_TX_INJECT_FRAME_IND
title: NDIS_WDI_TX_INJECT_FRAME_IND
author: windows-driver-content
description: The NdisWdiTxInjectFrameIndication callback function allows the LE to inject frames through the regular datapath (for example, authentication/association requests/responses, Wi-Fi Direct action frames).
old-location: netvista\ndiswditxinjectframeindication.htm
tech.root: netvista
ms.assetid: C384FAFF-E22D-4FA2-8B11-F6C046003C70
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NDIS_WDI_TX_INJECT_FRAME_IND, NDIS_WDI_TX_INJECT_FRAME_IND callback, NdisWdiTxInjectFrameIndication, NdisWdiTxInjectFrameIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxInjectFrameIndication, netvista.ndiswditxinjectframeindication
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
-	NdisWdiTxInjectFrameIndication
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_TX_INJECT_FRAME_IND callback function


## -description


The NdisWdiTxInjectFrameIndication callback function allows the LE to inject frames through the regular datapath (for example, authentication/association requests/responses, Wi-Fi Direct action frames).

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID. 


### -param PeerId [in]

The peer ID. When <b>TargetPriorityQueueing</b> is true, this must be set to the wildcard value.


### -param ExTid [in]

The extended TID.


### -param pNBL [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> chain.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn897820">WDI_EXEMPTION_ACTION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
 

 

