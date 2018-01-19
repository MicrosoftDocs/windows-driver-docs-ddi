---
UID: NS:d3d10umddi.D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
title: D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure describes a cube texture that is used to create a shader resource view in a call to the CreateShaderResourceView function.
old-location: display\d3d10ddiarg_texcube_shaderresourceview.htm
old-project: display
ms.assetid: ef45c368-37b9-4208-81d3-1ecab81268b0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW, D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
req.alt-loc: d3d10umddi.h
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
req.typenames: D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
---

# D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure



## -description
The D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure describes a cube texture that is used to create a shader resource view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a> function. 



## -syntax

````
typedef struct D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW {
  UINT MostDetailedMip;
  UINT MipLevels;
} D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW;
````


## -struct-fields

### -field MostDetailedMip

[in] The identifier of the most detailed MIP-map. 


### -field MipLevels

[in] The number of MIP-map levels for the texture. 


## -remarks
If the <b>MipLevels</b> member is set to -1, the MIP-maps in the texture start from the MIP-map that is set in the <b>MostDetailedMip</b> member. 


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

