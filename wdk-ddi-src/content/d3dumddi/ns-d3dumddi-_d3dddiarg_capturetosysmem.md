---
UID: NS:d3dumddi._D3DDDIARG_CAPTURETOSYSMEM
title: _D3DDDIARG_CAPTURETOSYSMEM (d3dumddi.h)
description: The D3DDDIARG_CAPTURETOSYSMEM structure describes the parameters of a bit-block transfer (bitblt) from a capture buffer to a video memory surface.
old-location: display\d3dddiarg_capturetosysmem.htm
tech.root: display
ms.assetid: 8cf42c60-655a-4deb-9351-4a3505b49593
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_CAPTURETOSYSMEM, D3DDDIARG_CAPTURETOSYSMEM structure [Display Devices], UMDisplayDriver_param_Structs_497b7e52-066f-4078-b673-0f9cd3b6f4c1.xml, _D3DDDIARG_CAPTURETOSYSMEM, d3dumddi/D3DDDIARG_CAPTURETOSYSMEM, display.d3dddiarg_capturetosysmem
f1_keywords:
 - "d3dumddi/D3DDDIARG_CAPTURETOSYSMEM"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_CAPTURETOSYSMEM
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CAPTURETOSYSMEM
---

# _D3DDDIARG_CAPTURETOSYSMEM structure


## -description


The D3DDDIARG_CAPTURETOSYSMEM structure describes the parameters of a bit-block transfer (bitblt) from a capture buffer to a video memory surface. 


## -struct-fields




### -field hSrcResource

[in] A handle to the source resource.


### -field SrcRect

[in] A <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure for the source rectangle. 


### -field hDstResource

[in] A handle to the destination resource.


### -field DstSubResourceIndex

[in] The index to the destination surface within the resource. 


### -field DstRect

[in] A <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure for the destination rectangle. 


## -remarks



Because the source resource that is specified by the <b>hSrcResource</b> member is a capture buffer, it is guaranteed to be a stand alone resource. Therefore, in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_capturetosysmem">CaptureToSysMem</a>, the Microsoft Direct3D runtime is not required to supply an index to a sub source surface within the resource. However, an index to a sub source surface is required when the runtime calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_blt">Blt</a> function to perform a more general bitblt.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_blt">Blt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_capturetosysmem">CaptureToSysMem</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>
 

 

