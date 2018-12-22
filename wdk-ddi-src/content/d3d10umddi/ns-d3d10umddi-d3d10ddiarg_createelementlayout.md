---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEELEMENTLAYOUT
title: D3D10DDIARG_CREATEELEMENTLAYOUT
description: The D3D10DDIARG_CREATEELEMENTLAYOUT structure describes the element layout to create.
old-location: display\d3d10ddiarg_createelementlayout.htm
ms.assetid: 3eb1555b-3274-496d-b6af-9cb0a6083ee4
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_CREATEELEMENTLAYOUT, D3D10DDIARG_CREATEELEMENTLAYOUT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_8c912e61-9cff-46ad-963f-16d3b9a13b10.xml, d3d10umddi/D3D10DDIARG_CREATEELEMENTLAYOUT, display.d3d10ddiarg_createelementlayout
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10DDIARG_CREATEELEMENTLAYOUT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_CREATEELEMENTLAYOUT
---

# D3D10DDIARG_CREATEELEMENTLAYOUT structure


## -description


The D3D10DDIARG_CREATEELEMENTLAYOUT structure describes the element layout to create.


## -struct-fields




### -field pVertexElements

[in] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541717">D3D10DDIARG_INPUT_ELEMENT_DESC</a> structures that describes each element in the element layout. 


### -field NumElements

[in] The number of elements in that array that the <b>pVertexElements</b> member specifies. 


## -see-also




<a href="https://msdn.microsoft.com/9fc80cea-8e4a-467a-b232-74333d2ceb5f">CalcPrivateElementLayoutSize</a>



<a href="https://msdn.microsoft.com/5af2189a-a064-4c62-be09-733c1d632983">CreateElementLayout</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541717">D3D10DDIARG_INPUT_ELEMENT_DESC</a>
 

 

