---
UID: NC:dot11wdi.NDIS_WDI_FREE_WDI_FRAME_METADATA
title: NDIS_WDI_FREE_WDI_FRAME_METADATA
author: windows-driver-content
description: The NdisWdiFreeWiFiFrameMetaData callback function frees a frame metadata buffer.
old-location: netvista\ndiswdifreewdiframemetadata.htm
old-project: netvista
ms.assetid: 828C181F-918A-4674-B6CE-FCB9750948E0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_WDI_FREE_WDI_FRAME_METADATA, NdisWdiFreeWiFiFrameMetaData, NdisWdiFreeWiFiFrameMetaData callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiFreeWiFiFrameMetaData, netvista.ndiswdifreewdiframemetadata
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
-	NdisWdiFreeWiFiFrameMetaData
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_FREE_WDI_FRAME_METADATA callback


## -description


The NdisWdiFreeWiFiFrameMetaData callback function frees a frame metadata buffer.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.


## -prototype


````
NDIS_WDI_FREE_WDI_FRAME_METADATA NdisWdiFreeWiFiFrameMetaData;

VOID NdisWdiFreeWiFiFrameMetaData(
  _In_ NDIS_HANDLE         NdisMiniportDataPathHandle,
  _In_ PWDI_FRAME_METADATA pWiFiFrameMetaData
)
{ ... }
````


## -parameters




### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param pWiFiFrameMetaData [in]

The frame metadata buffer to free.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



<a href="..\dot11wdi\ns-dot11wdi-_wdi_frame_metadata.md">WDI_FRAME_METADATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_FREE_WDI_FRAME_METADATA callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

