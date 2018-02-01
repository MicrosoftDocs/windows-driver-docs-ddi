---
UID: NC:dot11wdi.MINIPORT_WDI_POST_ADAPTER_PAUSE
title: MINIPORT_WDI_POST_ADAPTER_PAUSE
author: windows-driver-content
description: The MiniportWdiPostAdapterPause handler function is called by the Microsoft component after it finishes the data path clean up as part of the NDIS MiniportPause requirements.
old-location: netvista\miniportwdipostadapterpause.htm
old-project: netvista
ms.assetid: 57B52C5B-D151-4112-8173-23D18C636E98
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwdipostadapterpause, MiniportWdiPostAdapterPause callback function [Network Drivers Starting with Windows Vista], MiniportWdiPostAdapterPause, MINIPORT_WDI_POST_ADAPTER_PAUSE, MINIPORT_WDI_POST_ADAPTER_PAUSE, dot11wdi/MiniportWdiPostAdapterPause
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
-	MiniportWdiPostAdapterPause
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_POST_ADAPTER_PAUSE callback


## -description


The MiniportWdiPostAdapterPause handler function is called by the Microsoft component after it finishes the data path clean up as part of the NDIS <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a> requirements.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

The NDIS <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a> requirements are handled by the Microsoft component. As part of <i>MiniportPause</i>, it stops the data path and waits for it to clean up. The WDI IHV miniport can optionally register for a <i>MiniportWdiPostAdapterPause</i> callback that is called by the Microsoft component after it finishes the data path cleanup.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_POST_ADAPTER_PAUSE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_POST_ADAPTER_PAUSE MiniportWdiPostAdapterPause;

NDIS_STATUS MiniportWdiPostAdapterPause(
  _In_ NDIS_HANDLE                     MiniportAdapterContext,
  _In_ PNDIS_MINIPORT_PAUSE_PARAMETERS PauseParameters
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


### -param PauseParameters [in]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_miniport_pause_parameters.md">NDIS_MINIPORT_PAUSE_PARAMETERS</a> structure that defines the pause parameters for the miniport adapter.


## -returns


The return value is only used for logging/informational purposes.



## -see-also

<a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_pause_parameters.md">NDIS_MINIPORT_PAUSE_PARAMETERS</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_POST_ADAPTER_PAUSE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

