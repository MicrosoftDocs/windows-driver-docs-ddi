---
UID: NC:dot11wdi.NDIS_WDI_RX_STOP_CONFIRM
title: NDIS_WDI_RX_STOP_CONFIRM (dot11wdi.h)
description: The NdisWdiRxStopConfirm callback function indicates completion of a MiniportWdiRxStop request.
old-location: netvista\ndiswdirxstopconfirm.htm
tech.root: netvista
ms.assetid: 2022915A-2717-4098-BCD8-34130A161967
ms.date: 05/02/2018
ms.keywords: NDIS_WDI_RX_STOP_CONFIRM, NDIS_WDI_RX_STOP_CONFIRM callback, NdisWdiRxStopConfirm, NdisWdiRxStopConfirm callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiRxStopConfirm, netvista.ndiswdirxstopconfirm
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
-	NdisWdiRxStopConfirm
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_RX_STOP_CONFIRM callback function


## -description


The 
  NdisWdiRxStopConfirm callback function indicates completion of a <a href="https://msdn.microsoft.com/AAFECA64-07D7-43E6-ABFB-C0C85A9C03CD">MiniportWdiRxStop</a> request.  If traffic is stopped across the entire adapter, the target must stop indicating frames that match the stop request to the host prior to issuing  <b>NdisWdiRxStopConfirm</b>.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/AAFECA64-07D7-43E6-ABFB-C0C85A9C03CD">MiniportWdiRxStop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>
 

 

