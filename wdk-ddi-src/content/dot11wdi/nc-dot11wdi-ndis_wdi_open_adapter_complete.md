---
UID: NC:dot11wdi.NDIS_WDI_OPEN_ADAPTER_COMPLETE
title: NDIS_WDI_OPEN_ADAPTER_COMPLETE (dot11wdi.h)
description: The NdisWdiOpenAdapterComplete callback function is called by the IHV when an Open Task operation from MiniportWdiOpenAdapter has been successfully started.
old-location: netvista\ndiswdiopenadaptercomplete.htm
tech.root: netvista
ms.assetid: FD6FF134-A8D7-433E-9353-88965E67749E
ms.date: 05/02/2018
keywords: ["NDIS_WDI_OPEN_ADAPTER_COMPLETE callback function"]
ms.keywords: NDIS_WDI_OPEN_ADAPTER_COMPLETE, NDIS_WDI_OPEN_ADAPTER_COMPLETE callback, NdisWdiOpenAdapterComplete, NdisWdiOpenAdapterComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiOpenAdapterComplete, netvista.ndiswdiopenadaptercomplete
f1_keywords:
 - "dot11wdi/NdisWdiOpenAdapterComplete"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dot11wdi.h
api_name:
- NdisWdiOpenAdapterComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_OPEN_ADAPTER_COMPLETE callback function


## -description


The NdisWdiOpenAdapterComplete callback function is called by the IHV when an Open Task operation from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_open_adapter">MiniportWdiOpenAdapter</a> has been successfully started.

This is a control path callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle.


### -param CompletionStatus [in]

The completion status.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_open_adapter">MiniportWdiOpenAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>
 

 

