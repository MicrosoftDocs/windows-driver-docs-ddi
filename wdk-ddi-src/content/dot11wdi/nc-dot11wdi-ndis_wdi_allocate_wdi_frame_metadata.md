---
UID: NC:dot11wdi.NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA
title: NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA
author: windows-driver-content
description: The NdisWdiAllocateWiFiFrameMetaData callback function allocates a frame metadata buffer.
old-location: netvista\ndiswdiallocatewdiframemetadata.htm
old-project: netvista
ms.assetid: 6C565DAF-3363-466F-AC4A-9DB534E581FC
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA, NdisWdiAllocateWiFiFrameMetaData, NdisWdiAllocateWiFiFrameMetaData callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiAllocateWiFiFrameMetaData, netvista.ndiswdiallocatewdiframemetadata
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
-	NdisWdiAllocateWiFiFrameMetaData
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA callback


## -description


The NdisWdiAllocateWiFiFrameMetaData callback function  allocates a frame metadata buffer.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


## -returns



The allocated frame metadata buffer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn897827">WDI_FRAME_METADATA</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_ALLOCATE_WDI_FRAME_METADATA callback function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

