---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE
title: PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE
author: windows-driver-content
description: The CalcPrivateDepthStencilViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil view.
old-location: display\calcprivatedepthstencilviewsize.htm
old-project: display
ms.assetid: e5dfa018-f9a5-467f-8e84-9697d5f94689
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateDepthStencilViewSize, CalcPrivateDepthStencilViewSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE, UserModeDisplayDriverDx10_Functions_514ed3bc-fc1d-4bda-bcc9-f90e6900c002.xml, d3d10umddi/CalcPrivateDepthStencilViewSize, display.calcprivatedepthstencilviewsize
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
-	CalcPrivateDepthStencilViewSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback


## -description


The <b>CalcPrivateDepthStencilViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil view.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateDepthStencilView [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541658">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateDepthStencilViewSize</b> returns the size of the memory region that the driver requires for creating a depth stencil view.




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541658">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
 

 

