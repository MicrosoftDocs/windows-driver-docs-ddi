---
UID: NC:dot11wdi.NDIS_WDI_TX_QUERY_RA_TID_STATE
title: NDIS_WDI_TX_QUERY_RA_TID_STATE
author: windows-driver-content
description: The NdisWdiTxQueryRATIDState callback function is used by the TxEngine to query the state of a RA/TID or Port queue.
old-location: netvista\ndiswditxqueryratidstate.htm
old-project: netvista
ms.assetid: 76949336-3349-4869-83C7-60D7D8A6BE24
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_TX_QUERY_RA_TID_STATE, NdisWdiTxQueryRATIDState, NdisWdiTxQueryRATIDState callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxQueryRATIDState, netvista.ndiswditxqueryratidstate
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
-	NdisWdiTxQueryRATIDState
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_TX_QUERY_RA_TID_STATE callback


## -description


The NdisWdiTxQueryRATIDState callback function is used by the TxEngine to query the state of a RA/TID or Port queue.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID.


### -param PeerId [in]

The peer ID.


### -param ExTid [in]

The Extended Traffic ID (TID)


### -param *pWifiStatus [out]

Indicates the result of the query operation.  See the <i>Remarks</i> section for more information.


### -param pQueueLength [out]

The number of backlogged frames in the specified RA/TID  or Port queue.


## -returns



This callback function does not return a value.




## -remarks



The TxMgr returns a success status if the port and peer are valid. Otherwise, it returns an error status.  In the case of a success status, the <i>QueueLength</i> is set to the number of backlogged frames in the specified RA/TID  or Port queue.

If <b>TargetPriorityQueueing</b> is true, <a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a> must be set to the wildcard peer value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898187">WDI_TXRX_CAPABILITIES</a>
 

 

