---
UID: NC:dot11wdi.MINIPORT_WDI_POST_ADAPTER_RESTART
title: MINIPORT_WDI_POST_ADAPTER_RESTART
author: windows-driver-content
description: The MiniportWdiPostAdapterRestart handler function is called by the Microsoft component after it finishes restarting the data path as part of the NDIS MiniportRestart requirements.
old-location: netvista\miniportwdipostadapterrestart.htm
old-project: netvista
ms.assetid: 1686A3CA-AD4A-4560-8665-9AFBE920CDDA
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_WDI_POST_ADAPTER_RESTART, MiniportWdiPostAdapterRestart, MiniportWdiPostAdapterRestart callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiPostAdapterRestart, netvista.miniportwdipostadapterrestart
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
-	MiniportWdiPostAdapterRestart
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_POST_ADAPTER_RESTART callback


## -description


The MiniportWdiPostAdapterRestart handler function is called by the Microsoft component after it finishes restarting the data path as part of the NDIS <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> requirements.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

The NDIS <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> requirements are handled by the Microsoft component. As part of <i>MiniportRestart</i>, it undoes the data path pause work that it performed as part of <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>. The WDI IHV miniport can optionally register for a <i>MiniportWdiPostAdapterRestart</i> callback that is called by the Microsoft component after it finishes restarting the data path.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_POST_ADAPTER_RESTART</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_POST_ADAPTER_RESTART MiniportWdiPostAdapterRestart;

NDIS_STATUS MiniportWdiPostAdapterRestart(
  _In_ NDIS_HANDLE                       MiniportAdapterContext,
  _In_ PNDIS_MINIPORT_RESTART_PARAMETERS RestartParameters
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


### -param RestartParameters [in]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_miniport_restart_parameters.md">NDIS_MINIPORT_RESTART_PARAMETERS</a> structure that defines the restart parameters for the miniport adapter.


## -returns



MiniportWdiPostAdapterRestart can return any of the following return values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The driver successfully restarted the flow of network data through the miniport adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The restart failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The driver indicates <b>NDIS_STATUS_FAILURE</b> if none of the preceding values applies.

</td>
</tr>
</table>
 




## -see-also

<a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>



<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_restart_parameters.md">NDIS_MINIPORT_RESTART_PARAMETERS</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



 

 


