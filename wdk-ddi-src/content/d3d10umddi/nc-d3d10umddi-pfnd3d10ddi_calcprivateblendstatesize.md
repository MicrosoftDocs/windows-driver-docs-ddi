---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE
title: PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE
author: windows-driver-content
description: The CalcPrivateBlendStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
old-location: display\calcprivateblendstatesize.htm
old-project: display
ms.assetid: c13862b0-3136-4a95-bb00-6057f2934068
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateBlendStateSize, CalcPrivateBlendStateSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE, UserModeDisplayDriverDx10_Functions_bb7c2ca6-61c8-4f54-a635-4ec9fb539837.xml, d3d10umddi/CalcPrivateBlendStateSize, display.calcprivateblendstatesize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	CalcPrivateBlendStateSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE callback


## -description


The <b>CalcPrivateBlendStateSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.


## -prototype


````
PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE CalcPrivateBlendStateSize;

SIZE_T APIENTRY CalcPrivateBlendStateSize(
  _In_       D3D10DDI_HDEVICE     hDevice,
  _In_ const D3D10_DDI_BLEND_DESC *pBlendDesc
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pBlendDesc [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_blend_desc.md">D3D10_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateBlendStateSize</b> returns the size of the memory region that the driver requires for creating a blend state.




## -remarks



None.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_blend_desc.md">D3D10_DDI_BLEND_DESC</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 


