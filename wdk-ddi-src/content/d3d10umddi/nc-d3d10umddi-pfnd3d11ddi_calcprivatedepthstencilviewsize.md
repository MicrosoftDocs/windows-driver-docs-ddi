---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE
title: PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE
author: windows-driver-content
description: The CalcPrivateDepthStencilViewSize(D3D11) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth-stencil view.
old-location: display\calcprivatedepthstencilviewsize_d3d11_.htm
old-project: display
ms.assetid: d92e3bde-9527-401e-aafd-4ba39603d4a7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateDepthStencilViewSize, CalcPrivateDepthStencilViewSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE, UserModeDisplayDriverDx11_Functions_865f13d6-ea1c-4e9f-94b2-7f77d10c8283.xml, d3d10umddi/CalcPrivateDepthStencilViewSize, display.calcprivatedepthstencilviewsize_d3d11_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateDepthStencilViewSize(D3D11) is supported beginning with the Windows 7 operating system.
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
-	CalcPrivateDepthStencilViewSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback


## -description


The <b>CalcPrivateDepthStencilViewSize(D3D11)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth-stencil view.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateDepthStencilView [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542048">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateDepthStencilViewSize(D3D11)</b> returns the size of the memory region that the driver requires to create a depth-stencil view.




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542048">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>
 

 

