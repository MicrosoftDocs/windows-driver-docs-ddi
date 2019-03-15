---
UID: NS:d3d10umddi.D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
title: D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW (d3d10umddi.h)
description: The D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the CreateShaderResourceView function.
old-location: display\d3d10ddiarg_buffer_shaderresourceview.htm
ms.assetid: 9144b167-7fa4-4854-bf0c-e98192f07db8
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW, D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_76ff32e8-1460-45a7-a63d-3c18b75a860e.xml, d3d10umddi/D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW, display.d3d10ddiarg_buffer_shaderresourceview
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW
---

# D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure


## -description


The D3D10DDIARG_BUFFER_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the <a href="https://msdn.microsoft.com/3b1c998d-3fde-4712-ba74-7c8033033182">CreateShaderResourceView</a> function. 


## -struct-fields




### -field FirstElement


### -field ElementOffset

[in] The offset (that is, the number of elements) between the beginning of the buffer and the first element that is to be used in the view, starting at 0. 


### -field NumElements


### -field ElementWidth

[in] The number of elements in the view. 


## -see-also




<a href="https://msdn.microsoft.com/2abf5ca9-974b-40d7-b71c-43c4fb33dd7c">CalcPrivateShaderResourceViewSize</a>



<a href="https://msdn.microsoft.com/3b1c998d-3fde-4712-ba74-7c8033033182">CreateShaderResourceView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541708">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>
 

 

