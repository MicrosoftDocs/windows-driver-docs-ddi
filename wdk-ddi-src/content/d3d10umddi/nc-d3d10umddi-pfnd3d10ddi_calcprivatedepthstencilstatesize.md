---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE
title: PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE
author: windows-driver-content
description: The CalcPrivateDepthStencilStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil state.
old-location: display\calcprivatedepthstencilstatesize.htm
old-project: display
ms.assetid: dcc02e1e-97e0-4ccd-8329-8219cad5d09a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateDepthStencilStateSize, CalcPrivateDepthStencilStateSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE, UserModeDisplayDriverDx10_Functions_9eb00c77-fbc0-443d-848b-b7e254de4efe.xml, d3d10umddi/CalcPrivateDepthStencilStateSize, display.calcprivatedepthstencilstatesize
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
-	CalcPrivateDepthStencilStateSize
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE callback


## -description


The <b>CalcPrivateDepthStencilStateSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil state.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pDepthStencilDesc [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541944">D3D10_DDI_DEPTH_STENCIL_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateDepthStencilStateSize</b> returns the size of the memory region that the driver requires for creating a depth stencil state.




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541944">D3D10_DDI_DEPTH_STENCIL_DESC</a>
 

 

