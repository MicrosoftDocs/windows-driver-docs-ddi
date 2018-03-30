---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_PALETTE_0020
title: D3D12DDI_VIDEO_PROCESS_PALETTE_0020
author: windows-driver-content
description: Specifies whether the palette is enabled and an array of palette entries.
old-location: display\d3d12ddi_video_process_palette.htm
old-project: display
ms.assetid: 25AA9012-64A1-4E61-956F-7F30CE0639EA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_PALETTE_0020, D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_PALETTE_0020, display.d3d12ddi_video_process_palette
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_PALETTE_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_PALETTE_0020
---

# D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure


## -description


Specifies whether the palette is enabled and an array of palette entries. 


## -struct-fields




### -field Enable

Whether palette is enabled.


### -field NumEntries

The number of elements in the <b>pEntries</b> array.


### -field pEntries

A pointer to an array of palette entries. For RGB streams, the palette entries use the <b>DXGI_FORMAT_B8G8R8A8</b> representation. For YCbCr streams, the palette entries use the <b>DXGI_FORMAT_AYUV</b> representation. For more information, see the <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> enumeration. The caller allocates the array.


## -see-also




<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>
 

 

