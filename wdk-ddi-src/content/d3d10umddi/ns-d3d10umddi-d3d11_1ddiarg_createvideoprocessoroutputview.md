---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW
title: D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW
description: Describes the video processor's output view.
old-location: display\d3d11_1ddiarg_createvideoprocessoroutputview.htm
ms.assetid: 3545AE6F-3D9E-4C3B-8C22-B823A18CC700
ms.date: 05/10/2018
ms.keywords: D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW, D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW structure [Display Devices], PD3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW, PD3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW structure pointer [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW, d3d10umddi/PD3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW, display.d3d11_1ddiarg_createvideoprocessoroutputview
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	d3d10umddi.h
api_name:
-	D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW
---

# D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW structure


## -description


Describes the video processor's output view.


## -struct-fields




### -field hDrvResource

A handle to the video decoder output resource.


### -field hDrvVideoProcessorEnum

A handle to the video processor enumeration.


### -field MipSlice

The identifier of the MIP-map slice.


### -field FirstArraySlice

The identifier of the first array slice.


### -field ArraySize

The number of array slices for the texture.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406318">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a>
 

 

