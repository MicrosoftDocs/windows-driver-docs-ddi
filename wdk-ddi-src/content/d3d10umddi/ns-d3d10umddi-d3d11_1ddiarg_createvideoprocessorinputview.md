---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW
title: D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW (d3d10umddi.h)
description: Describes the video processor's input view.
old-location: display\d3d11_1ddiarg_createvideoprocessorinputview.htm
ms.assetid: 73F8F146-A38B-4890-867D-862361455AD4
ms.date: 05/10/2018
ms.keywords: D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW structure [Display Devices], PD3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, PD3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW structure pointer [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, d3d10umddi/PD3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, display.d3d11_1ddiarg_createvideoprocessorinputview
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW
---

# D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW structure


## -description


Describes the video processor's input view.


## -struct-fields




### -field hDrvResource

A handle to the video decoder input resource.


### -field hDrvVideoProcessorEnum

A handle to the video processor enumeration.


### -field FourCC

A FOURCC code that the application uses to override the surface format. A value of zero indicates that the application will not override the resource format.

For example, if a new video standard emerges that requires a new substream format, the application can create an equivelant surface using a standard format and then specify a FOURCC code when it creates a view to indicate that the data is laid out according to the new video standard.

For more information about FOURCC codes, see <a href="https://go.microsoft.com/fwlink/p/?linkid=231686">Video FOURCCs</a>.


### -field MipSlice

The identifier of the MIP-map slice.


### -field FirstArraySlice

The identifier of the first array slice.


### -field ArraySize

The number of array slices for the texture.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessoroutputview">D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW</a>
 

 

