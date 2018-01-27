---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_STOP
title: MINIPORT_WDI_TAL_TXRX_STOP
author: windows-driver-content
description: The MiniportWdiTalTxRxStop handler function stops TXRX communication between the TAL and the target.
old-location: netvista\miniportwditaltxrxstop.htm
old-project: netvista
ms.assetid: 21841DC6-B95F-4372-BBD1-EA195832A118
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwditaltxrxstop, MiniportWdiTalTxRxStop callback function [Network Drivers Starting with Windows Vista], MiniportWdiTalTxRxStop, MINIPORT_WDI_TAL_TXRX_STOP, MINIPORT_WDI_TAL_TXRX_STOP, dot11wdi/MiniportWdiTalTxRxStop
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
-	MiniportWdiTalTxRxStop
product: Windows
targetos: Windows
req.typenames: *PSYNTH_STATS, SYNTH_STATS
---

# MINIPORT_WDI_TAL_TXRX_STOP callback


## -description


The 
  MiniportWdiTalTxRxStop handler function stops TXRX communication between the TAL and the target.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_STOP</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_TAL_TXRX_STOP MiniportWdiTalTxRxStop;

VOID MiniportWdiTalTxRxStop(
  _In_ TAL_TXRX_HANDLE MiniportTalTxRxContext
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


## -returns


This callback function does not return a value.



## -see-also

<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TAL_TXRX_STOP callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

