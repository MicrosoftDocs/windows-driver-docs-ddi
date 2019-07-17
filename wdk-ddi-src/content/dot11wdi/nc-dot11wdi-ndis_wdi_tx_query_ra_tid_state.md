---
UID: NC:dot11wdi.NDIS_WDI_TX_QUERY_RA_TID_STATE
title: NDIS_WDI_TX_QUERY_RA_TID_STATE (dot11wdi.h)
description: The NdisWdiTxQueryRATIDState callback function is used by the TxEngine to query the state of a RA/TID or Port queue.
old-location: netvista\ndiswditxqueryratidstate.htm
tech.root: netvista
ms.assetid: 76949336-3349-4869-83C7-60D7D8A6BE24
ms.date: 05/02/2018
ms.keywords: NDIS_WDI_TX_QUERY_RA_TID_STATE, NDIS_WDI_TX_QUERY_RA_TID_STATE callback, NdisWdiTxQueryRATIDState, NdisWdiTxQueryRATIDState callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxQueryRATIDState, netvista.ndiswditxqueryratidstate
ms.topic: callback
f1_keywords:
 - "dot11wdi/NdisWdiTxQueryRATIDState"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dot11wdi.h
api_name:
- NdisWdiTxQueryRATIDState
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_TX_QUERY_RA_TID_STATE callback function


## -description


The NdisWdiTxQueryRATIDState callback function is used by the TxEngine to query the state of a RA/TID or Port queue.

This is a callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


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

If <b>TargetPriorityQueueing</b> is true, <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a> must be set to the wildcard peer value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-extended-tid">WDI_EXTENDED_TID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_wdi_txrx_target_capabilities">WDI_TXRX_CAPABILITIES</a>
 

 

