---
UID: NC:dot11wdi.MINIPORT_WDI_POST_ADAPTER_PAUSE
title: MINIPORT_WDI_POST_ADAPTER_PAUSE
author: windows-driver-content
description: The MiniportWdiPostAdapterPause handler function is called by the Microsoft component after it finishes the data path clean up as part of the NDIS MiniportPause requirements.
old-location: netvista\miniportwdipostadapterpause.htm
tech.root: netvista
ms.assetid: 57B52C5B-D151-4112-8173-23D18C636E98
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: MINIPORT_WDI_POST_ADAPTER_PAUSE, MINIPORT_WDI_POST_ADAPTER_PAUSE callback, MiniportWdiPostAdapterPause, MiniportWdiPostAdapterPause callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiPostAdapterPause, netvista.miniportwdipostadapterpause
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
-	MiniportWdiPostAdapterPause
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_POST_ADAPTER_PAUSE callback function


## -description


The MiniportWdiPostAdapterPause handler function is called by the Microsoft component after it finishes the data path clean up as part of the NDIS <a href="https://msdn.microsoft.com/047241a5-6f52-4a82-a334-8508f0de5e1a">MiniportPause</a> requirements.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

The NDIS <a href="https://msdn.microsoft.com/047241a5-6f52-4a82-a334-8508f0de5e1a">MiniportPause</a> requirements are handled by the Microsoft component. As part of <i>MiniportPause</i>, it stops the data path and waits for it to clean up. The WDI IHV miniport can optionally register for a <i>MiniportWdiPostAdapterPause</i> callback that is called by the Microsoft component after it finishes the data path cleanup.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_POST_ADAPTER_PAUSE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


### -param PauseParameters [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566473">NDIS_MINIPORT_PAUSE_PARAMETERS</a> structure that defines the pause parameters for the miniport adapter.


## -returns



The return value is only used for logging/informational purposes.




## -see-also




<a href="https://msdn.microsoft.com/047241a5-6f52-4a82-a334-8508f0de5e1a">MiniportPause</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566473">NDIS_MINIPORT_PAUSE_PARAMETERS</a>
 

 

