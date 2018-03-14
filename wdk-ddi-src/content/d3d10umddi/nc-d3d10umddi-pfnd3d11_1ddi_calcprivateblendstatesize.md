---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE
title: PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE
author: windows-driver-content
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
old-location: display\calcprivateblendstatesize_d3d11_1_.htm
old-project: display
ms.assetid: e53bb658-ef6c-4f44-aa5a-8c641046f90d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateBlendStateSize(D3D11_1), CalcPrivateBlendStateSize(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE, d3d10umddi/CalcPrivateBlendStateSize(D3D11_1), display.calcprivateblendstatesize_d3d11_1_, display.pfncalcprivateblendstatesize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CalcPrivateBlendStateSize(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE callback


## -description


Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.


## -prototype


````
PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE CalcPrivateBlendStateSize(D3D11_1);

SIZE_T APIENTRY* CalcPrivateBlendStateSize(D3D11_1)(
             D3D10DDI_HDEVICE       hDevice,
  _In_ const D3D11_1_DDI_BLEND_DESC pBlendDesc
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice

A handle to the display device (graphics context).


#### - pBlendDesc [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_blend_desc.md">D3D11_1_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.


## -returns



The size of the memory region that the driver requires for creating a blend state.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_blend_desc.md">D3D11_1_DDI_BLEND_DESC</a>



 

 


