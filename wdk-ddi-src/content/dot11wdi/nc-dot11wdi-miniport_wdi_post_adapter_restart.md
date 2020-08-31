---
UID: NC:dot11wdi.MINIPORT_WDI_POST_ADAPTER_RESTART
title: MINIPORT_WDI_POST_ADAPTER_RESTART (dot11wdi.h)
description: The MiniportWdiPostAdapterRestart handler function is called by the Microsoft component after it finishes restarting the data path as part of the NDIS MiniportRestart requirements.
old-location: netvista\miniportwdipostadapterrestart.htm
tech.root: netvista
ms.assetid: 1686A3CA-AD4A-4560-8665-9AFBE920CDDA
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_POST_ADAPTER_RESTART callback function"]
ms.keywords: MINIPORT_WDI_POST_ADAPTER_RESTART, MINIPORT_WDI_POST_ADAPTER_RESTART callback, MiniportWdiPostAdapterRestart, MiniportWdiPostAdapterRestart callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiPostAdapterRestart, netvista.miniportwdipostadapterrestart
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
targetos: Windows
req.typenames: 
f1_keywords:
 - MINIPORT_WDI_POST_ADAPTER_RESTART
 - dot11wdi/MINIPORT_WDI_POST_ADAPTER_RESTART
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiPostAdapterRestart
---

# MINIPORT_WDI_POST_ADAPTER_RESTART callback function


## -description

The MiniportWdiPostAdapterRestart handler function is called by the Microsoft component after it finishes restarting the data path as part of the NDIS <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a> requirements.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

The NDIS <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a> requirements are handled by the Microsoft component. As part of <i>MiniportRestart</i>, it undoes the data path pause work that it performed as part of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a>. The WDI IHV miniport can optionally register for a <i>MiniportWdiPostAdapterRestart</i> callback that is called by the Microsoft component after it finishes restarting the data path.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_POST_ADAPTER_RESTART</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportAdapterContext 

[in]
The handle to the context area that the miniport driver allocated.

### -param RestartParameters 

[in]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_restart_parameters">NDIS_MINIPORT_RESTART_PARAMETERS</a> structure that defines the restart parameters for the miniport adapter.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_restart_parameters">NDIS_MINIPORT_RESTART_PARAMETERS</a>

