---
UID: NC:dot11wdi.NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA
title: NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA (dot11wdi.h)
description: The NdisWdiAllocateWiFiFrameMetaData callback function allocates a frame metadata buffer.
old-location: netvista\ndiswdiallocatewdiframemetadata.htm
tech.root: netvista
ms.assetid: 6C565DAF-3363-466F-AC4A-9DB534E581FC
ms.date: 05/02/2018
ms.keywords: NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA, NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA callback, NdisWdiAllocateWiFiFrameMetaData, NdisWdiAllocateWiFiFrameMetaData callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiAllocateWiFiFrameMetaData, netvista.ndiswdiallocatewdiframemetadata
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dot11wdi.h
api_name:
- NdisWdiAllocateWiFiFrameMetaData
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA callback function


## -description


The NdisWdiAllocateWiFiFrameMetaData callback function  allocates a frame metadata buffer.

This is a callback inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


## -returns



The allocated frame metadata buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dot11wdi/ns-dot11wdi-_wdi_frame_metadata">WDI_FRAME_METADATA</a>
 

 

