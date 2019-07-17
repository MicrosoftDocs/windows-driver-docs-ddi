---
UID: NC:dot11wdi.NDIS_WDI_TX_ABORT_CONFIRM
title: NDIS_WDI_TX_ABORT_CONFIRM (dot11wdi.h)
description: The NdisWdiTxAbortConfirm callback function indicates an asynchronous confirmation of a MiniportWdiTxAbort from WDI.
old-location: netvista\ndiswditxabortconfirm.htm
tech.root: netvista
ms.assetid: 1619BF14-DDEE-48CB-8E31-0CC17C8A4C6A
ms.date: 05/02/2018
ms.keywords: NDIS_WDI_TX_ABORT_CONFIRM, NDIS_WDI_TX_ABORT_CONFIRM callback, NdisWdiTxAbortConfirm, NdisWdiTxAbortConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxAbortConfirm, netvista.ndiswditxabortconfirm
ms.topic: callback
f1_keywords:
 - "dot11wdi/NdisWdiTxAbortConfirm"
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
- NdisWdiTxAbortConfirm
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_TX_ABORT_CONFIRM callback function


## -description


The NdisWdiTxAbortConfirm callback function  indicates an asynchronous confirmation of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tx_abort">MiniportWdiTxAbort</a> from WDI.

This is a callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>
 

 

