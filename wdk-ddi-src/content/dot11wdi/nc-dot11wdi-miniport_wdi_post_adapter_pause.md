---
UID: NC:dot11wdi.MINIPORT_WDI_POST_ADAPTER_PAUSE
title: MINIPORT_WDI_POST_ADAPTER_PAUSE (dot11wdi.h)
description: The MiniportWdiPostAdapterPause handler function is called by the Microsoft component after it finishes the data path clean up as part of the NDIS MiniportPause requirements.
old-location: netvista\miniportwdipostadapterpause.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_POST_ADAPTER_PAUSE callback function"]
ms.keywords: MINIPORT_WDI_POST_ADAPTER_PAUSE, MINIPORT_WDI_POST_ADAPTER_PAUSE callback, MiniportWdiPostAdapterPause, MiniportWdiPostAdapterPause callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiPostAdapterPause, netvista.miniportwdipostadapterpause
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
 - MINIPORT_WDI_POST_ADAPTER_PAUSE
 - dot11wdi/MINIPORT_WDI_POST_ADAPTER_PAUSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MINIPORT_WDI_POST_ADAPTER_PAUSE
---

# MINIPORT_WDI_POST_ADAPTER_PAUSE callback function


## -description

The MiniportWdiPostAdapterPause handler function is called by the Microsoft component after it finishes the data path clean up as part of the NDIS <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> requirements.

This is a WDI miniport handler inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

The NDIS <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> requirements are handled by the Microsoft component. As part of <i>MiniportPause</i>, it stops the data path and waits for it to clean up. The WDI IHV miniport can optionally register for a <i>MiniportWdiPostAdapterPause</i> callback that is called by the Microsoft component after it finishes the data path cleanup.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_POST_ADAPTER_PAUSE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportAdapterContext 

[in]
The handle to the context area that the miniport driver allocated.

### -param PauseParameters 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pause_parameters">NDIS_MINIPORT_PAUSE_PARAMETERS</a> structure that defines the pause parameters for the miniport adapter.

## -returns

The return value is only used for logging/informational purposes.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pause_parameters">NDIS_MINIPORT_PAUSE_PARAMETERS</a>

