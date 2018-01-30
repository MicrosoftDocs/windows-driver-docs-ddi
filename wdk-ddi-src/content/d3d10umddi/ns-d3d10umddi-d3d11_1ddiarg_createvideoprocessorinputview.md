---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW
title: D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW
author: windows-driver-content
description: Describes the video processor's input view.
old-location: display\d3d11_1ddiarg_createvideoprocessorinputview.htm
old-project: display
ms.assetid: 73F8F146-A38B-4890-867D-862361455AD4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, PD3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, d3d10umddi/PD3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW structure [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, display.d3d11_1ddiarg_createvideoprocessorinputview, PD3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW structure pointer [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW
---

# D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW structure


## -description


Describes the video processor's input view.


## -syntax


````
typedef struct _D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW {
  D3D10DDI_HRESOURCE             hDrvResource;
  D3D11_1DDI_HVIDEOPROCESSORENUM hDrvVideoProcessorEnum;
  UINT                           FourCC;
  UINT                           MipSlice;
  UINT                           FirstArraySlice;
  UINT                           ArraySize;
} D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW, *PD3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW;
````


## -struct-fields




### -field hDrvResource

A handle to the video decoder input resource.


### -field hDrvVideoProcessorEnum

A handle to the video processor enumeration.


### -field FourCC

A FOURCC code that the application uses to override the surface format. A value of zero indicates that the application will not override the resource format.

For example, if a new video standard emerges that requires a new substream format, the application can create an equivelant surface using a standard format and then specify a FOURCC code when it creates a view to indicate that the data is laid out according to the new video standard.

For more information about FOURCC codes, see <a href="http://go.microsoft.com/fwlink/p/?linkid=231686">Video FOURCCs</a>.


### -field MipSlice

The identifier of the MIP-map slice.


### -field FirstArraySlice

The identifier of the first array slice.


### -field ArraySize

The number of array slices for the texture.


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessoroutputview.md">D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

