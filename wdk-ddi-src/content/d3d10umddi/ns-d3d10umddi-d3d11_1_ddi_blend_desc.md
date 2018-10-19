---
UID: NS:d3d10umddi.D3D11_1_DDI_BLEND_DESC
title: D3D11_1_DDI_BLEND_DESC
author: windows-driver-content
description: Describes a blend state. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\d3d11_1_ddi_blend_desc.htm
ms.assetid: 1f633261-82b2-4346-b1c2-cd36228af5f4
ms.date: 05/10/2018
ms.keywords: D3D11_1_DDI_BLEND_DESC, D3D11_1_DDI_BLEND_DESC structure [Display Devices], d3d10umddi/D3D11_1_DDI_BLEND_DESC, display.d3d11_1_ddi_blend_desc
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1_DDI_BLEND_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1_DDI_BLEND_DESC
---

# D3D11_1_DDI_BLEND_DESC structure


## -description


 Describes a blend state. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -struct-fields




### -field AlphaToCoverageEnable

[in] A Boolean value that specifies whether transparency coverage is enabled. <b>TRUE</b> indicates transparency coverage is enabled; <b>FALSE</b> indicates transparency coverage is disabled. This member is relevant for multiple-sample antialiasing only.


### -field IndependentBlendEnable

[in] A Boolean value that specifies only whether the <a href="https://msdn.microsoft.com/e53bb658-ef6c-4f44-aa5a-8c641046f90d">CalcPrivateBlendStateSize(D3D11_1)</a> function replicated the first entry in the array that the <b>RenderTarget</b> member specifies to the other entries of that array. <b>TRUE</b> indicates the first entry was not replicated; <b>FALSE</b> indicates that the first entry in the array in the <b>RenderTarget</b> member is replicated to the other entries of the array.


### -field RenderTarget

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451056">D3D11_1_DDI_RENDER_TARGET_BLEND_DESC</a> structures that indicate the blend state for each associated render target.


## -see-also




<a href="https://msdn.microsoft.com/e53bb658-ef6c-4f44-aa5a-8c641046f90d">CalcPrivateBlendStateSize(D3D11_1)</a>



<a href="https://msdn.microsoft.com/5956412e-ae35-4960-afc0-a82c6a2aa9f1">CreateBlendState(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451056">D3D11_1_DDI_RENDER_TARGET_BLEND_DESC</a>
 

 

