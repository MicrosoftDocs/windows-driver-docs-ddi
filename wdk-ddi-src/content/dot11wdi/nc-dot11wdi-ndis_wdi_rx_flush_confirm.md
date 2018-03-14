---
UID: NC:dot11wdi.NDIS_WDI_RX_FLUSH_CONFIRM
title: NDIS_WDI_RX_FLUSH_CONFIRM
author: windows-driver-content
description: The NdisWdiRxFlushConfirm callback function indicates completion of a MiniportWdiRxFlush request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing NdisWdiRxFlushConfirm.
old-location: netvista\ndiswdirxflushconfirm.htm
old-project: netvista
ms.assetid: CEED709C-F295-4633-B7C1-4719EDDC7CD4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_WDI_RX_FLUSH_CONFIRM, NdisWdiRxFlushConfirm, NdisWdiRxFlushConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiRxFlushConfirm, netvista.ndiswdirxflushconfirm
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
-	NdisWdiRxFlushConfirm
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_RX_FLUSH_CONFIRM callback


## -description


The NdisWdiRxFlushConfirm callback function indicates completion of a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_flush.md">MiniportWdiRxFlush</a> request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing <i>NdisWdiRxFlushConfirm</i>.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_RX_FLUSH_CONFIRM NdisWdiRxFlushConfirm;

VOID NdisWdiRxFlushConfirm(
   NDIS_HANDLE NdisMiniportDataPathHandle
)
{ ... }
````


## -parameters




### -param NdisMiniportDataPathHandle

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_flush.md">MiniportWdiRxFlush</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>



 

 


