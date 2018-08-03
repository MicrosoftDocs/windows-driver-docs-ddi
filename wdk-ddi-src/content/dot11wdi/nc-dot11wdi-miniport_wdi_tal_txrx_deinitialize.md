---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_DEINITIALIZE
title: MINIPORT_WDI_TAL_TXRX_DEINITIALIZE
author: windows-driver-content
description: The MiniportWdiTalTxRxDeinitialize handler function is invoked in the context of miniport halt. The functional components RXEngine and TxEngine have already been stopped and any pending data frames completed/returned.
old-location: netvista\miniportwditaltxrxdeinitialize.htm
tech.root: netvista
ms.assetid: E8A77709-7E35-4FFC-B7EC-19E5256AB55F
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_DEINITIALIZE, MINIPORT_WDI_TAL_TXRX_DEINITIALIZE callback, MiniportWdiTalTxRxDeinitialize, MiniportWdiTalTxRxDeinitialize callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxDeinitialize, netvista.miniportwditaltxrxdeinitialize
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
-	MiniportWdiTalTxRxDeinitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_DEINITIALIZE callback function


## -description


The 
  MiniportWdiTalTxRxDeinitialize handler function is invoked in the context of miniport halt. The functional components RXEngine and TxEngine have already been stopped and any pending data frames completed/returned.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_DEINITIALIZE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>
 

 

