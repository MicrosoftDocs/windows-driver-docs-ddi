---
UID: NC:dot11wdi.MINIPORT_WDI_RX_PPDU_RSSI
title: MINIPORT_WDI_RX_PPDU_RSSI
author: windows-driver-content
description: The MiniportWdiRxPpduRssi handler function returns the absolute value of RSSI (in dB) for the PPDU. The RxMgr may request the RSSI only once per data indication using the PNET_BUFFER_LIST obtained from MiniportWdiRxGetMpdus.
old-location: netvista\miniportwdirxppdurssi.htm
old-project: netvista
ms.assetid: 34C34C42-E5E1-44F6-AC81-ADC77206DED0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: MINIPORT_WDI_RX_PPDU_RSSI, MiniportWdiRxPpduRssi, MiniportWdiRxPpduRssi callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxPpduRssi, netvista.miniportwdirxppdurssi
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
-	MiniportWdiRxPpduRssi
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_RX_PPDU_RSSI callback


## -description


The 
  MiniportWdiRxPpduRssi handler function returns the absolute value of RSSI (in dB) for the PPDU. The RxMgr may request the RSSI only once per data indication using the PNET_BUFFER_LIST obtained from <a href="https://msdn.microsoft.com/195F4143-4889-4788-BAF5-2F1ED6E4E50A">MiniportWdiRxGetMpdus</a>.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_PPDU_RSSI</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param pNBL [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> for which the RSSI is requested.


### -param *pRssi [out]

The absolute value of RSSI, in dB.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>
 

 

