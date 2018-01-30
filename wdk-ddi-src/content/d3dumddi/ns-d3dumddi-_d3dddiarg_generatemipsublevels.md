---
UID: NS:d3dumddi._D3DDDIARG_GENERATEMIPSUBLEVELS
title: "_D3DDDIARG_GENERATEMIPSUBLEVELS"
author: windows-driver-content
description: The D3DDDIARG_GENERATEMIPSUBLEVELS structure describes how to generate the sublevels of a MIP-map texture.
old-location: display\d3dddiarg_generatemipsublevels.htm
old-project: display
ms.assetid: 19c08206-cde8-4ec2-bbd1-92eadeecdb90
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddiarg_generatemipsublevels, d3dumddi/D3DDDIARG_GENERATEMIPSUBLEVELS, D3DDDIARG_GENERATEMIPSUBLEVELS, D3DDDIARG_GENERATEMIPSUBLEVELS structure [Display Devices], _D3DDDIARG_GENERATEMIPSUBLEVELS, UMDisplayDriver_param_Structs_4000d18b-18c0-4499-bfbe-a3f5e866553b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_GENERATEMIPSUBLEVELS
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GENERATEMIPSUBLEVELS
---

# _D3DDDIARG_GENERATEMIPSUBLEVELS structure


## -description


The D3DDDIARG_GENERATEMIPSUBLEVELS structure describes how to generate the sublevels of a MIP-map texture. 


## -syntax


````
typedef struct _D3DDDIARG_GENERATEMIPSUBLEVELS {
  HANDLE                  hResource;
  D3DDDITEXTUREFILTERTYPE Filter;
} D3DDDIARG_GENERATEMIPSUBLEVELS;
````


## -struct-fields




### -field hResource

[in] A handle to the MIP-map texture surface.


### -field Filter

[in] A D3DDDITEXTUREFILTERTYPE-typed value that indicates the texture magnification or minification filter type that is used in generating the sublevels of the MIP-map texture. This member can be one of the following values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDDITEXF_NONE

</td>
<td>
MIP-map filtering is disabled.

</td>
</tr>
<tr>
<td>
D3DDDITEXF_POINT

</td>
<td>
Point filtering. The texel with coordinates that are nearest to the required pixel value is used. The texture filter to be used between MIP-map levels is nearest-point MIP-map filtering.

</td>
</tr>
<tr>
<td>
D3DDDITEXF_LINEAR

</td>
<td>
Bilinear-interpolation filtering. A weighted average of a 2x2 area of texels that surround the required pixel is used. The texture filter to use between MIP-map levels is trilinear MIP-map interpolation. 

</td>
</tr>
<tr>
<td>
D3DDDITEXF_ANISOTROPIC

</td>
<td>
Anisotropic texture filtering. This filtering compensates for distortion that is caused by the difference in angle between the texture polygon and the plane of the screen.

</td>
</tr>
<tr>
<td>
D3DDDITEXF_PYRAMIDALQUAD

</td>
<td>
Four-sample tent filtering.

</td>
</tr>
<tr>
<td>
D3DDDITEXF_GAUSSIANQUAD

</td>
<td>
Four-sample Gaussian filtering.

</td>
</tr>
</table> 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_generatemipsublevels.md">GenerateMipSubLevels</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_GENERATEMIPSUBLEVELS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

