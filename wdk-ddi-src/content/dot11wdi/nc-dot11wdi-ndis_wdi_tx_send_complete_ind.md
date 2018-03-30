---
UID: NC:dot11wdi.NDIS_WDI_TX_SEND_COMPLETE_IND
title: NDIS_WDI_TX_SEND_COMPLETE_IND
author: windows-driver-content
description: The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames.
old-location: netvista\ndiswditxsendcompleteindication.htm
old-project: netvista
ms.assetid: A38BA15D-FDD8-41D1-87ED-2CABC1926962
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_TX_SEND_COMPLETE_IND, NdisWdiTxSendCompleteIndication, NdisWdiTxSendCompleteIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxSendCompleteIndication, netvista.ndiswditxsendcompleteindication
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
-	NdisWdiTxSendCompleteIndication
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_TX_SEND_COMPLETE_IND callback


## -description


The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.

Frames with different TX status values are completed in separate indications.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param WifiTxFrameStatus [in]

The TX status, specified as a <a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a> value.


### -param NumCompletedSends [in]

The number of completed sends.


### -param *WifiTxFrameIdList [in]

An array of frame IDs. The size of the array is the value of <i>NumCompletedSends</i>.


### -param *WifiTxCompleteList [in, optional]

An array of TX completion data. The size of the array is the value of <i>NumCompletedSends</i>.


## -returns



This callback function does not return a value.




## -remarks




<a href="https://msdn.microsoft.com/library/windows/hardware/dn898193">WDI_TX_COMPLETE_DATA</a> is optional for all status values unless the indicated frames are sent over-the-air and have a status of <b>WDI_TxFrameStatus_SendPostponed</b>. In that case, <b>WDI_TX_COMPLETE_DATA</b> is required.

A TX completion with a frame with <b>WDI_TxFrameStatus_SendPostponed</b> is identical to an <a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a> with <b>WDI_TX_PAUSE_REASON_PS</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898193">WDI_TX_COMPLETE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898196">WDI_TX_PAUSE_REASON</a>
 

 

