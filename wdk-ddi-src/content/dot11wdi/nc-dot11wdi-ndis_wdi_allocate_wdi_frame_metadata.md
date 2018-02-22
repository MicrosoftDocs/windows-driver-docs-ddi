---
UID: NC:dot11wdi.NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA
title: NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA
author: windows-driver-content
description: The NdisWdiAllocateWiFiFrameMetaData callback function allocates a frame metadata buffer.
old-location: netvista\ndiswdiallocatewdiframemetadata.htm
old-project: netvista
ms.assetid: 6C565DAF-3363-466F-AC4A-9DB534E581FC
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndiswdiallocatewdiframemetadata, NdisWdiAllocateWiFiFrameMetaData callback function [Network Drivers Starting with Windows Vista], NdisWdiAllocateWiFiFrameMetaData, NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA, NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA, dot11wdi/NdisWdiAllocateWiFiFrameMetaData
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
-	NdisWdiAllocateWiFiFrameMetaData
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---

# NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA callback


## -description


The NdisWdiAllocateWiFiFrameMetaData callback function  allocates a frame metadata buffer.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA NdisWdiAllocateWiFiFrameMetaData;

PWDI_FRAME_METADATA NdisWdiAllocateWiFiFrameMetaData(
  _In_ NDIS_HANDLE NdisMiniportDataPathHandle
)
{ ... }
````


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


## -returns



The allocated frame metadata buffer.




## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_wdi_frame_metadata.md">WDI_FRAME_METADATA</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

