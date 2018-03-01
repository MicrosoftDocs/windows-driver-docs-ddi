---
UID: NC:dot11wdi.MINIPORT_WDI_RX_THROTTLE
title: MINIPORT_WDI_RX_THROTTLE
author: windows-driver-content
description: The MiniportWdiRxThrottle handler function tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs.
old-location: netvista\miniportwdirxthrottle.htm
old-project: netvista
ms.assetid: A5985C6D-3768-4ACE-B52B-3D3494334114
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_WDI_RX_THROTTLE, MiniportWdiRxThrottle, MiniportWdiRxThrottle callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxThrottle, netvista.miniportwdirxthrottle
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
-	MiniportWdiRxThrottle
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_RX_THROTTLE callback


## -description


The 
  MiniportWdiRxThrottle handler function  tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_THROTTLE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_RX_THROTTLE MiniportWdiRxThrottle;

VOID MiniportWdiRxThrottle(
  _In_ TAL_TXRX_HANDLE       MiniportTalTxRxContext,
  _In_ WDI_RX_THROTTLE_LEVEL RxThrottleLevel
)
{ ... }
````


## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param RxThrottleLevel [in]

A <a href="..\dot11wdi\ne-dot11wdi-_wdi_rx_throttle_level.md">WDI_RX_THROTTLE_LEVEL</a> enumeration value that specifies the throttle level.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_rx_throttle_level.md">WDI_RX_THROTTLE_LEVEL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_RX_THROTTLE callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

