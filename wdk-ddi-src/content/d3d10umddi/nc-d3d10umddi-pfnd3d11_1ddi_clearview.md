---
UID: NC:d3d10umddi.PFND3D11_1DDI_CLEARVIEW
title: PFND3D11_1DDI_CLEARVIEW (d3d10umddi.h)
description: Sets all the elements in a resource view to one value. A resource view is a surface descriptor that indicates a format and possibly a subset of the resource.
old-location: display\clearview.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CLEARVIEW callback function"]
ms.keywords: ClearView, ClearView callback function [Display Devices], PFND3D11_1DDI_CLEARVIEW, PFND3D11_1DDI_CLEARVIEW callback, d3d10umddi/ClearView, display.clearview, display.clearview_d3d11_1_, display.pfnclearview
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_CLEARVIEW
 - d3d10umddi/PFND3D11_1DDI_CLEARVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - ClearView
product:
 - Windows
---

# PFND3D11_1DDI_CLEARVIEW callback function


## -description

Sets all the elements in a resource view to one value. A resource view is  a surface descriptor  that indicates a format and possibly a subset of the resource.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param viewType

A value, of type <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_handletype">D3D11DDI_HANDLETYPE</a>, that identifies the view handle type that supports this clear operation. Possible types are the following.

<ul>
<li><b>D3D10DDI_HT_RENDERTARGETVIEW</b></li>
<li><b>D3D11DDI_HT_UNORDEREDACCESSVIEW</b></li>
<li>Any <b>D3D11_1DDI_HT_VIDEOXXX</b> type</li>
</ul>

### -param hView

A pointer to the resource view to clear.

### -param Color

[4]
A 4-component array that represents the color to use to clear the resource view. For more details, see the Remarks section.

### -param pRect

An array of <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structures for the rectangles in the resource view to clear. If <b>NULL</b>, <i>ClearView</i> clears the entire surface.

### -param NumRects

The number of rectangles in the array that the  <i>pRect</i> parameter specifies.

## -remarks

<i>ClearView</i> works only on render-target views (RTVs), unordered-access views (UAVs), or any video view of a <a href="/windows-hardware/drivers/display/details-of-the-extended-format">Texture2D</a> surface. Empty rectangles in the <i>pRect</i> array are a no-op. A rectangle is empty if the top value equals the bottom value or the left value equals the right value.

<i>ClearView</i> does not support 3-D textures.

<i>ClearView</i> applies the same color value to all array slices in a view; all rectangles in the <i>pRect</i> array correspond to each array slice.  The <i>pRect</i> array of rectangles is a set of areas to clear on a single surface.  If the view is an array, <i>ClearView</i> clears all the rectangles on each array slice individually.

When the user-mode driver applies rectangles to buffers, it should set the top value to 0 and the bottom value to 1 and set the left value and right value to describe the extent within the buffer. When the top value equals the bottom value or the left value equals the right value, the rectangle is empty and a no-op is achieved.

The driver should convert and clamp color values to the destination format as appropriate per Direct3D conversion rules.  For example, if the format of the view is <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT_R8G8B8A8_UNORM</a>, clamp inputs to 0.0f to 1.0f (+INF -> 1.0f (0XFF)/NaN -> 0.0f).

If the format is integer, such as <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT_R8G8B8A8_UINT</a>, take inputs as integral floats. Therefore, 235.0f maps to 235 (rounds to zero, out of range/INF values clamp to target range, and NaN to zero).

Here are the color mappings:

* Color[0]: R (or Y for video)
* Color[1]: G (or U/Cb for video)
* Color[2]: B (or V/Cr for video)
* Color[3]: A

For video views with YUV or YCbBr formats, <i>ClearView</i> does not convert color values. In situations where the format name does not indicate _UNORM,  _UINT, and so on, <i>ClearView</i> assumes _UINT. Therefore, 235.0f maps to 235 (rounds to zero, out of range/INF values clamp to target range, and NaN to zero).

For Microsoft Direct3D views of the subsampled RTV or UAV video surfaces, note that the dimensions of the view are based on how many pixels are in the view format rather than the underlying logical number of video pixels.  For example suppose the surface has format YUY2 with dimension 1920 by 1080 pixels and an RTV uses the format <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT_R8G8B8A8_UINT</a>.  The view appears to Direct3D as having 1920/2 = 960 <b>R8G8B8A8</b> pixels in the horizontal direction.  So any rectangles passed into <i>ClearView</i> are interpreted in this space.  Furthermore, the clear value is taken for all 4 components, <b>R8G8B8A8</b>, as if it is no different from a true <b>R8G8B8A8</b> surface.  In this case, R, G, B, and A do not mean standard RGBA color values; instead, they identify a location in memory, and the caller is responsible for understanding what it means to put data into that location in the context of a video surface.

However, video views of a video surface (such as views provided to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview">CreateVideoDecoderOutputView</a> function and other <b>XxxInputView</b> and <b>XxxOutputView</b> functions) appear at the full logical dimensions. In this case, the horizontal dimension is 1920 pixels wide, so <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structures passed into <i>ClearView</i> honor that. Such  <b>RECT</b>s  must be aligned so they do not straddle subsampled blocks, otherwise the runtime will drop the call to this function. For video views, YUV colors must be appropriately replicated for subsampled formats. For example, YUV in the <i>ClearView</i> call has the Y value duplicated for each block in a YUY2 surface.


The <b>D3D10_DDI_RECT</b> structure is defined as a <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structure.

```cpp
typedef RECT D3D10_DDI_RECT;
```

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview">CreateVideoDecoderOutputView</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_handletype">D3D11DDI_HANDLETYPE</a>



<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>
