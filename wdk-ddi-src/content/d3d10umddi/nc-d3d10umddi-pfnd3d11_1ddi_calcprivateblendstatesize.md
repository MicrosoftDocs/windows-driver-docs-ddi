---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE
title: PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE
author: windows-driver-content
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
old-location: display\calcprivateblendstatesize_d3d11_1_.htm
tech.root: display
ms.assetid: e53bb658-ef6c-4f44-aa5a-8c641046f90d
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CalcPrivateBlendStateSize(D3D11_1), CalcPrivateBlendStateSize(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE, PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE callback, d3d10umddi/CalcPrivateBlendStateSize(D3D11_1), display.calcprivateblendstatesize_d3d11_1_, display.pfncalcprivateblendstatesize
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE callback function


## -description


Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.


## -parameters




### -param Arg1


### -param *








#### - hDevice

A handle to the display device (graphics context).


#### - pBlendDesc [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451041">D3D11_1_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.


## -returns



The size of the memory region that the driver requires for creating a blend state.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451041">D3D11_1_DDI_BLEND_DESC</a>
 

 

