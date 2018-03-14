---
UID: NC:d3d10umddi.PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE
title: PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE
author: windows-driver-content
description: The CalcPrivateBlendStateSize(D3D10_1) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
old-location: display\calcprivateblendstatesize_d3d10_1_.htm
old-project: display
ms.assetid: 6f48290e-d571-4e59-9f33-58398db5b6fb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateBlendStateSize_d3d10_1_, CalcPrivateBlendStateSize_d3d10_1_ callback function [Display Devices], PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE, UserModeDisplayDriverDx10_Functions_e5473d10-1ef3-4c7c-9908-a6f3818da267.xml, d3d10umddi/CalcPrivateBlendStateSize_d3d10_1_, display.calcprivateblendstatesize_d3d10_1_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateBlendStateSize(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CalcPrivateBlendStateSize_d3d10_1_
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE callback


## -description


The <b>CalcPrivateBlendStateSize(D3D10_1)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.


## -prototype


````
PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE CalcPrivateBlendStateSize_d3d10_1_;

SIZE_T APIENTRY CalcPrivateBlendStateSize_d3d10_1_(
  _In_       D3D10DDI_HDEVICE       hDevice,
  _In_ const D3D10_1_DDI_BLEND_DESC *pBlendDesc
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pBlendDesc [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1_ddi_blend_desc.md">D3D10_1_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateBlendStateSize(D3D10_1)</b> returns the size of the memory region that the driver requires for creating a blend state.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1_ddi_blend_desc.md">D3D10_1_DDI_BLEND_DESC</a>



 

 


