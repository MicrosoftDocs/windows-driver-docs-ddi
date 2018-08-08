---
UID: NC:dot11wdi.NDIS_WDI_RX_FLUSH_CONFIRM
title: NDIS_WDI_RX_FLUSH_CONFIRM
author: windows-driver-content
description: The NdisWdiRxFlushConfirm callback function indicates completion of a MiniportWdiRxFlush request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing NdisWdiRxFlushConfirm.
old-location: netvista\ndiswdirxflushconfirm.htm
tech.root: netvista
ms.assetid: CEED709C-F295-4633-B7C1-4719EDDC7CD4
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NDIS_WDI_RX_FLUSH_CONFIRM, NDIS_WDI_RX_FLUSH_CONFIRM callback, NdisWdiRxFlushConfirm, NdisWdiRxFlushConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiRxFlushConfirm, netvista.ndiswdirxflushconfirm
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_RX_FLUSH_CONFIRM callback function


## -description


The NdisWdiRxFlushConfirm callback function indicates completion of a <a href="https://msdn.microsoft.com/76945A84-A6DB-4753-B04E-32249359B8C6">MiniportWdiRxFlush</a> request. The RxEngine must complete the discard of all RX data frames that match the flush request prior to issuing <i>NdisWdiRxFlushConfirm</i>.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/76945A84-A6DB-4753-B04E-32249359B8C6">MiniportWdiRxFlush</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>
 

 

