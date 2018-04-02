---
UID: NC:dot11wdi.NDIS_WDI_TX_ABORT_CONFIRM
title: NDIS_WDI_TX_ABORT_CONFIRM
author: windows-driver-content
description: The NdisWdiTxAbortConfirm callback function indicates an asynchronous confirmation of a MiniportWdiTxAbort from WDI.
old-location: netvista\ndiswditxabortconfirm.htm
old-project: netvista
ms.assetid: 1619BF14-DDEE-48CB-8E31-0CC17C8A4C6A
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_TX_ABORT_CONFIRM, NdisWdiTxAbortConfirm, NdisWdiTxAbortConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxAbortConfirm, netvista.ndiswditxabortconfirm
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
-	NdisWdiTxAbortConfirm
product:
- Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_TX_ABORT_CONFIRM callback


## -description


The NdisWdiTxAbortConfirm callback function  indicates an asynchronous confirmation of a <a href="https://msdn.microsoft.com/FA6BEAE9-5D48-463E-A398-518737D78867">MiniportWdiTxAbort</a> from WDI.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>
 

 

