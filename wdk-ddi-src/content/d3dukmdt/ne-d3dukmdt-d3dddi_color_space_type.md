---
UID: NE:d3dukmdt.D3DDDI_COLOR_SPACE_TYPE
title: D3DDDI_COLOR_SPACE_TYPE
author: windows-driver-content
description: Defines stream color space information.
old-location: display\d3dddi_color_space_type.htm
tech.root: display
ms.assetid: 0A26F0AC-2D00-4847-96ED-3232A067F7CC
ms.date: 04/16/2018
ms.keywords: D3DDDI_COLOR_SPACE_CUSTOM, D3DDDI_COLOR_SPACE_RESERVED, D3DDDI_COLOR_SPACE_RGB_FULL_G10_NONE_P709, D3DDDI_COLOR_SPACE_RGB_FULL_G2084_NONE_P2020, D3DDDI_COLOR_SPACE_RGB_FULL_G22_NONE_P709, D3DDDI_COLOR_SPACE_RGB_STUDIO_G2084_NONE_P2020, D3DDDI_COLOR_SPACE_RGB_STUDIO_G22_NONE_P2020, D3DDDI_COLOR_SPACE_RGB_STUDIO_G22_NONE_P709, D3DDDI_COLOR_SPACE_TYPE, D3DDDI_COLOR_SPACE_TYPE enumeration [Display Devices], D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P2020, D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P601, D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P709, D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_NONE_P709_X601, D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G2084_LEFT_P2020, D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G2084_TOPLEFT_P2020, D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P2020, D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P601, D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P709, D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_TOPLEFT_P2020, D3DDDI_COLOR_SPACE_YCBCR_STUDIO_GHLG_TOPLEFT_P2020, DD3DDDI_COLOR_SPACE_RGB_FULL_G22_NONE_P2020, DD3DDDI_COLOR_SPACE_YCBCR_FULL_GHLG_TOPLEFT_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_CUSTOM, d3dukmdt/D3DDDI_COLOR_SPACE_RESERVED, d3dukmdt/D3DDDI_COLOR_SPACE_RGB_FULL_G10_NONE_P709, d3dukmdt/D3DDDI_COLOR_SPACE_RGB_FULL_G2084_NONE_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_RGB_FULL_G22_NONE_P709, d3dukmdt/D3DDDI_COLOR_SPACE_RGB_STUDIO_G2084_NONE_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_RGB_STUDIO_G22_NONE_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_RGB_STUDIO_G22_NONE_P709, d3dukmdt/D3DDDI_COLOR_SPACE_TYPE, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P601, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P709, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_NONE_P709_X601, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G2084_LEFT_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G2084_TOPLEFT_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P601, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P709, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_TOPLEFT_P2020, d3dukmdt/D3DDDI_COLOR_SPACE_YCBCR_STUDIO_GHLG_TOPLEFT_P2020, d3dukmdt/DD3DDDI_COLOR_SPACE_RGB_FULL_G22_NONE_P2020, d3dukmdt/DD3DDDI_COLOR_SPACE_YCBCR_FULL_GHLG_TOPLEFT_P2020, display.d3dddi_color_space_type
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dukmdt.h
api_name:
-	D3DDDI_COLOR_SPACE_TYPE
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_COLOR_SPACE_TYPE
---

# D3DDDI_COLOR_SPACE_TYPE enumeration


## -description


Defines stream color space information.


## -enum-fields




### -field D3DDDI_COLOR_SPACE_RGB_FULL_G22_NONE_P709

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>RGB</td>
</tr>
<tr>
<td>Range</td>
<td>0-255</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Image</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.709</td>
</tr>
</table>
 

This is the standard definition for <i>sRGB</i>.


Note that this is often implemented with a linear segment, but in that case the exponent is corrected to stay aligned with a gamma 2.2 curve.



This is usually used with 8 bit and 10 bit color channels.


### -field D3DDDI_COLOR_SPACE_RGB_FULL_G10_NONE_P709

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>RGB</td>
</tr>
<tr>
<td>Range</td>
<td>0-255</td>
</tr>
<tr>
<td>Gamma</td>
<td>1.0</td>
</tr>
<tr>
<td>Costing</td>
<td>Image</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.709</td>
</tr>
</table>
 

This is the standard definition for <i>scRGB</i>.



This is usually used with 16 bit integer, 16 bit floating point, and 32 bit floating point channels.



### -field D3DDDI_COLOR_SPACE_RGB_STUDIO_G22_NONE_P709

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>RGB</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Image</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.709</td>
</tr>
</table>
 

This is the standard definition for <i>ITU-R Recommendation BT.709</i>.  Note that due to the inclusion of a linear segment, the transfer curve looks similar to a pure exponential gamma of 1.9.



This is usually used with 8 bit and 10 bit color channels.


### -field D3DDDI_COLOR_SPACE_RGB_STUDIO_G22_NONE_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>RGB</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Image</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 

This is usually used with 10, 12, or 16 bit color channels.


### -field D3DDDI_COLOR_SPACE_RESERVED

Reserved for future use.


### -field D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_NONE_P709_X601

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>0-255</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Image</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.709</td>
</tr>
<tr>
<td>Transfer Matrix</td>
<td>BT.601</td>
</tr>
</table>
 

This definition is commonly used for <i>JPG</i>.



This is usually used with 8, 10, 12, or 16 bit color channels.


### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P601

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Video</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.601</td>
</tr>
</table>
 

This definition is commonly used for <i>MPEG2</i>.



This is usually used with 8, 10, 12, or 16 bit color channels.


### -field D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P601

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>0-255</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Video</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.601</td>
</tr>
</table>
 

This is sometimes used for <i>H.264</i> camera capture.



This is usually used with 8, 10, 12, or 16 bit color channels.



### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P709

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Video</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.709</td>
</tr>
</table>
 

This definition is commonly used for <i>H.264</i> and <i>HEVC</i>.



This is usually used with 8, 10, 12, or 16 bit color channels.


### -field D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P709

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>0-255</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Video</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.709</td>
</tr>
</table>
 

This is sometimes used for <i>H.264</i> camera capture.



This is usually used with 8, 10, 12, or 16 bit color channels.



### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_LEFT_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Video</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 

This definition may be used by <i>HEVC</i>.



This is usually used with 10, 12, or 16 bit color channels.


### -field D3DDDI_COLOR_SPACE_YCBCR_FULL_G22_LEFT_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>0-255</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Video</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 

This is usually used with 10, 12, or 16 bit color channels.


### -field D3DDDI_COLOR_SPACE_RGB_FULL_G2084_NONE_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>RGB</td>
</tr>
<tr>
<td>Range</td>
<td>0-255</td>
</tr>
<tr>
<td>Gamma</td>
<td>2084</td>
</tr>
<tr>
<td>Costing</td>
<td>Center</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 


### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G2084_LEFT_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2084</td>
</tr>
<tr>
<td>Costing</td>
<td>Left</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 


### -field D3DDDI_COLOR_SPACE_RGB_STUDIO_G2084_NONE_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>RGB</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2084</td>
</tr>
<tr>
<td>Costing</td>
<td>Center</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 


### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G22_TOPLEFT_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Costing</td>
<td>Top Left</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 


### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G2084_TOPLEFT_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2084</td>
</tr>
<tr>
<td>Costing</td>
<td>Top Left</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 


### -field D3DDDI_COLOR_SPACE_RGB_FULL_G22_NONE_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>RGB</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>2.2</td>
</tr>
<tr>
<td>Cositing</td>
<td>None</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>

### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_GHLG_TOPLEFT_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>16-235</td>
</tr>
<tr>
<td>Gamma</td>
<td>HLG</td>
</tr>
<tr>
<td>Cositing</td>
<td>Top Left</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 

This color space can be used as an input to the video processor DDIs, but will never be used to scan out.


### -field D3DDDI_COLOR_SPACE_YCBCR_FULL_GHLG_TOPLEFT_P2020

<table>
<tr>
<th>Property</th>
<th>Value</th>
</tr>
<tr>
<td>Colorspace</td>
<td>YCbCr</td>
</tr>
<tr>
<td>Range</td>
<td>0-255</td>
</tr>
<tr>
<td>Gamma</td>
<td>HLG</td>
</tr>
<tr>
<td>Cositing</td>
<td>Top Left</td>
</tr>
<tr>
<td>Primaries</td>
<td>BT.2020</td>
</tr>
</table>
 

This color space can be used as an input to the video processor DDIs, but will never be used to scan out.

### -field D3DDDI_COLOR_SPACE_RGB_STUDIO_G24_NONE_P709


### -field D3DDDI_COLOR_SPACE_RGB_STUDIO_G24_NONE_P2020


### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G24_LEFT_P709


### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G24_LEFT_P2020


### -field D3DDDI_COLOR_SPACE_YCBCR_STUDIO_G24_TOPLEFT_P2020


### -field D3DDDI_COLOR_SPACE_CUSTOM

A custom color definition is used.







## -remarks




The following color parameters are defined:



Subsampling and the layout of the color channels are inferred from the surface format.



