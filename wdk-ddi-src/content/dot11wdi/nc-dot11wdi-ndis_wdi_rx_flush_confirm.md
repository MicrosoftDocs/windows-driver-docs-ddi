---
UID: NC:dot11wdi.NDIS_WDI_RX_FLUSH_CONFIRM
title: NDIS_WDI_RX_FLUSH_CONFIRM
author: windows-driver-content
description: The NdisWdiRxFlushConfirm callback function indicates completion of a MiniportWdiRxFlush request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing NdisWdiRxFlushConfirm.
old-location: netvista\ndiswdirxflushconfirm.htm
old-project: netvista
ms.assetid: CEED709C-F295-4633-B7C1-4719EDDC7CD4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndiswdirxflushconfirm, NdisWdiRxFlushConfirm callback function [Network Drivers Starting with Windows Vista], NdisWdiRxFlushConfirm, NDIS_WDI_RX_FLUSH_CONFIRM, NDIS_WDI_RX_FLUSH_CONFIRM, dot11wdi/NdisWdiRxFlushConfirm
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

<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_flush.md">MiniportWdiRxFlush</a>

<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_RX_FLUSH_CONFIRM callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

