---
UID: NC:dot11wdi.MINIPORT_WDI_RX_RESTART
title: MINIPORT_WDI_RX_RESTART
author: windows-driver-content
description: The MiniportWdiRxRestart handler function configures the RxEngine to restart indicating data traffic. This is issued following a MiniportWdiRxStop.
old-location: netvista\miniportwdirxrestart.htm
old-project: netvista
ms.assetid: 465716C7-A157-4B06-BAE2-F18A08126040
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_WDI_RX_RESTART, MiniportWdiRxRestart, MiniportWdiRxRestart callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxRestart, netvista.miniportwdirxrestart
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
-	MiniportWdiRxRestart
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_RX_RESTART callback


## -description


The 
  MiniportWdiRxRestart handler function configures the RxEngine to restart indicating data traffic. This is issued following a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_stop.md">MiniportWdiRxStop</a>.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_RESTART</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_RX_RESTART MiniportWdiRxRestart;

VOID MiniportWdiRxRestart(
  _In_ TAL_TXRX_HANDLE MiniportTalTxRxContext,
  _In_ WDI_PORT_ID     PortId
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID.


## -returns



This callback function does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>



 

 


