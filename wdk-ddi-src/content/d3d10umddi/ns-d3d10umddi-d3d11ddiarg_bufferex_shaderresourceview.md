---
UID: NS:d3d10umddi.D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW
title: D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW (d3d10umddi.h)
description: The D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the CreateShaderResourceView(D3D11) function.
old-location: display\d3d11ddiarg_bufferex_shaderresourceview.htm
ms.assetid: b3585a06-fdb0-4fe9-8d5c-63680039a789
ms.date: 05/10/2018
ms.keywords: D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW, D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_49ef78b9-8a6f-4b67-bf2f-bae79086b6c7.xml, d3d10umddi/D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW, display.d3d11ddiarg_bufferex_shaderresourceview
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW is supported beginning with the Windows 7 operating system.
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
- D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW
---

# D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure


## -description


The D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview">CreateShaderResourceView(D3D11)</a> function. 


## -struct-fields




### -field FirstElement

[in] The offset, in bytes, to the first element in the buffer. 


### -field ElementOffset

[in] The offset, in bytes, to the first element in the buffer. 


### -field NumElements

[in] The number of elements in the buffer. 


### -field ElementWidth

[in] The width, in elements, in the buffer. 


### -field Flags

[in] A valid bitwise OR of flag values that describe the buffer. Currently, the Direct3D runtime supports only the D3D11_DDI_BUFFEREX_SRV_FLAG_RAW (0x00000001) flag. If this flag is set, the buffer is in raw format. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize(D3D11)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview">CreateShaderResourceView(D3D11)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createshaderresourceview">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a>
 

 

