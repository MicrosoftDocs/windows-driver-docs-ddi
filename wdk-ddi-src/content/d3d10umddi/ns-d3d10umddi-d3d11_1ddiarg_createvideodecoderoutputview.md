---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW
title: D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW
author: windows-driver-content
description: Describes the video decoder's output-view state.
old-location: display\d3d11_1ddiarg_createvideodecoderoutputview.htm
old-project: display
ms.assetid: 6DD555B1-01E8-48DE-B957-2752671B7EBB
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW, D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW structure [Display Devices], PD3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW, PD3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW structure pointer [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW, d3d10umddi/PD3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW, display.d3d11_1ddiarg_createvideodecoderoutputview
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
-	D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW
---

# D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW structure


## -description


Describes the video decoder's output-view state.


## -syntax


````
typedef struct _D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW {
  D3D10DDI_HRESOURCE hDrvResource;
  GUID               DecodeProfile;
  UINT               MipSlice;
  UINT               FirstArraySlice;
  UINT               ArraySize;
} D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW, *PD3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW;
````


## -struct-fields




### -field hDrvResource

A handle to the video decoder output resource.


### -field DecodeProfile

The decode profile to be used in conjunction with the encryption.


### -field MipSlice

The identifier of the MIP-map slice.


### -field FirstArraySlice

The identifier of the first array slice.


### -field ArraySize

The number of array slices for the texture.

