---
UID: NS:d3d10umddi.D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
title: D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure describes cube textures that are used to create a shader resource view in a call to the CreateShaderResourceView(D3D10_1) function.
old-location: display\d3d10_1ddiarg_texcube_shaderresourceview.htm
old-project: display
ms.assetid: 89d0b6fa-b990-43a9-a943-76d270b507cc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW, D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_4988e1af-5552-4f7c-be15-5c54f88b9975.xml, d3d10umddi/D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW, display.d3d10_1ddiarg_texcube_shaderresourceview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
-	D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
product: Windows
targetos: Windows
req.typenames: D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW
---

# D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure


## -description


The D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure describes cube textures that are used to create a shader resource view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview.md">CreateShaderResourceView(D3D10_1)</a> function. 


## -syntax


````
typedef struct D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW {
  UINT MostDetailedMip;
  UINT MipLevels;
  UINT First2DArrayFace;
  UINT NumCubes;
} D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW;
````


## -struct-fields




### -field MostDetailedMip

[in] The identifier of the most detailed MIP-map. 


### -field MipLevels

[in] The number of MIP-map levels for the texture. 


### -field First2DArrayFace

[in] The identifier of the first 2-D texture that comprises one or more cube textures. 


### -field NumCubes

[in] The number of cube textures for a shader resource view. 


## -remarks



The value in the <b>First2DArrayFace</b> member added with 6 multiplied by the number in the <b>NumCubes</b> member must be less than or equal to the value in the <b>ArraySize</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a> structure for the shader resource whose view is created in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview.md">CreateShaderResourceView(D3D10_1)</a> function. That is, the following calculation applies:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>::First2DArrayFace + 6 * ::NumCubes &lt;= Resource ::ArraySize</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_createshaderresourceview.md">CreateShaderResourceView(D3D10_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize(D3D10_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddiarg_createshaderresourceview.md">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_1DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

