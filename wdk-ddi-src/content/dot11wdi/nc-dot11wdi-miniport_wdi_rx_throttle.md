---
UID: NC:dot11wdi.MINIPORT_WDI_RX_THROTTLE
title: MINIPORT_WDI_RX_THROTTLE
author: windows-driver-content
description: The MiniportWdiRxThrottle handler function tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs.
old-location: netvista\miniportwdirxthrottle.htm
old-project: netvista
ms.assetid: A5985C6D-3768-4ACE-B52B-3D3494334114
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: MINIPORT_WDI_RX_THROTTLE, MINIPORT_WDI_RX_THROTTLE callback, MiniportWdiRxThrottle, MiniportWdiRxThrottle callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxThrottle, netvista.miniportwdirxthrottle
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
req.typenames: 
---

# MINIPORT_WDI_RX_THROTTLE callback function


## -description


The 
  MiniportWdiRxThrottle handler function  tells the TAL/target to enable mechanisms to reduce the rate of RX MSDUs.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_THROTTLE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param RxThrottleLevel [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn926113">WDI_RX_THROTTLE_LEVEL</a> enumeration value that specifies the throttle level.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn926113">WDI_RX_THROTTLE_LEVEL</a>
 

 

