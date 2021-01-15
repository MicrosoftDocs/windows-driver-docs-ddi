---
UID: NC:dot11wdi.NDIS_WDI_CLOSE_ADAPTER_COMPLETE
title: NDIS_WDI_CLOSE_ADAPTER_COMPLETE (dot11wdi.h)
description: The NdisWdiCloseAdapterComplete callback function is called by the IHV when a Close Task operation from MiniportWdiCloseAdapter has been successfully started.
old-location: netvista\ndiswdicloseadaptercomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WDI_CLOSE_ADAPTER_COMPLETE callback function"]
ms.keywords: NDIS_WDI_CLOSE_ADAPTER_COMPLETE, NDIS_WDI_CLOSE_ADAPTER_COMPLETE callback, NdisWdiCloseAdapterComplete, NdisWdiCloseAdapterComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiCloseAdapterComplete, netvista.ndiswdicloseadaptercomplete
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
 - NDIS_WDI_CLOSE_ADAPTER_COMPLETE
 - dot11wdi/NDIS_WDI_CLOSE_ADAPTER_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - NDIS_WDI_CLOSE_ADAPTER_COMPLETE
---

# NDIS_WDI_CLOSE_ADAPTER_COMPLETE callback function


## -description

The NdisWdiCloseAdapterComplete callback function is called by the IHV when a Close Task operation from <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_close_adapter">MiniportWdiCloseAdapter</a> has been successfully started.

This is a control path callback inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>.

## -parameters

### -param MiniportAdapterHandle 

[in]
The miniport handle.

### -param CompletionStatus 

[in]
The completion status.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_close_adapter">MiniportWdiCloseAdapter</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>

