---
UID: NC:dot11wdi.MINIPORT_WDI_RX_STOP
title: MINIPORT_WDI_RX_STOP
author: windows-driver-content
description: The MiniportWdiRxStop handler function stops RX on a given port and accepts the wildcard port ID to stop RX across the adapter.
old-location: netvista\miniportwdirxstop.htm
old-project: netvista
ms.assetid: AAFECA64-07D7-43E6-ABFB-C0C85A9C03CD
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: MINIPORT_WDI_RX_STOP, MINIPORT_WDI_RX_STOP callback, MiniportWdiRxStop, MiniportWdiRxStop callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxStop, netvista.miniportwdirxstop
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
-	MiniportWdiRxStop
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_RX_STOP callback function


## -description


The 
  MiniportWdiRxStop handler function stops RX on a given port and accepts the wildcard port ID  to stop RX across the adapter. The TAL completes the RX stop operation by completing the request with a success status, or by completing it with a pending status and asynchronously indicating <a href="https://msdn.microsoft.com/2022915A-2717-4098-BCD8-34130A161967">RxStopConfirm</a>.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.

Prior to completing the indication, the target must be configured to stop indicating new traffic on the selected port or the entire adapter.

This request is issued to the TAL as part of a transition to low power (adapter) and dot11 reset (port).
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_STOP</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID.


### -param *pWifiStatus [out]

Status from the IHV miniport. A success status indicates that the operation completion synchronously.  A pending status indicates that the stop will be asynchronously confirmed.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
 

 

