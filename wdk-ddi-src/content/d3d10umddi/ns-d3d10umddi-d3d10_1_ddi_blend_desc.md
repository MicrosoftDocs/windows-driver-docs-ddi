---
UID: NS:d3d10umddi.D3D10_1_DDI_BLEND_DESC
title: D3D10_1_DDI_BLEND_DESC
author: windows-driver-content
description: The D3D10_1_DDI_BLEND_DESC structure describes a blend state.
old-location: display\d3d10_1_ddi_blend_desc.htm
old-project: display
ms.assetid: e398b1a3-60bf-4a4a-b5c2-1dc11cf3dae1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10_1_DDI_BLEND_DESC, D3D10_1_DDI_BLEND_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_088d7013-3c56-4bfc-8e68-250b8e020a52.xml, d3d10umddi/D3D10_1_DDI_BLEND_DESC, display.d3d10_1_ddi_blend_desc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_1_DDI_BLEND_DESC is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10_1_DDI_BLEND_DESC
product: Windows
targetos: Windows
req.typenames: D3D10_1_DDI_BLEND_DESC
---

# D3D10_1_DDI_BLEND_DESC structure


## -description


The D3D10_1_DDI_BLEND_DESC structure describes a blend state.


## -struct-fields




### -field AlphaToCoverageEnable

[in] A Boolean value that specifies whether transparency coverage is enabled. <b>TRUE</b> indicates transparency coverage is enabled; <b>FALSE</b> indicates transparency coverage is disabled. This member is relevant for multiple-sample antialiasing only.


### -field IndependentBlendEnable

[in] A Boolean value that specifies only whether the <a href="https://msdn.microsoft.com/6f48290e-d571-4e59-9f33-58398db5b6fb">CalcPrivateBlendStateSize(D3D10_1)</a> function replicated the first entry in the array that the <b>RenderTarget</b> member specifies to the other entries of that array. <b>TRUE</b> indicates the first entry was not replicated; <b>FALSE</b> indicates that the first entry in the array in the <b>RenderTarget</b> member is replicated to the other entries of the array. 


### -field RenderTarget

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541990">D3D10_DDI_RENDER_TARGET_BLEND_DESC1</a> structures that indicate the blend state for each associated render target.


## -see-also




<a href="https://msdn.microsoft.com/6f48290e-d571-4e59-9f33-58398db5b6fb">CalcPrivateBlendStateSize(D3D10_1)</a>



<a href="https://msdn.microsoft.com/1b258f28-c386-477c-92d1-cb5918080dcf">CreateBlendState(D3D10_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541916">D3D10_DDI_BLEND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541923">D3D10_DDI_BLEND_OP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541990">D3D10_DDI_RENDER_TARGET_BLEND_DESC1</a>
 

 

