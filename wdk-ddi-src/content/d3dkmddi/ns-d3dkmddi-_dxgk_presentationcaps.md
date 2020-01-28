---
UID: NS:d3dkmddi._DXGK_PRESENTATIONCAPS
title: _DXGK_PRESENTATIONCAPS (d3dkmddi.h)
description: The DXGK_PRESENTATIONCAPS structure identifies presentation capabilities of a display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_presentationcaps.htm
ms.assetid: 38de4631-535f-4950-b361-d70f8c638c36
ms.date: 05/10/2018
ms.keywords: DXGK_PRESENTATIONCAPS, DXGK_PRESENTATIONCAPS structure [Display Devices], DmStructs_67f7af73-6eaa-4ac8-ad04-1633bc1504af.xml, _DXGK_PRESENTATIONCAPS, d3dkmddi/DXGK_PRESENTATIONCAPS, display.dxgk_presentationcaps
f1_keywords:
 - "d3dkmddi/DXGK_PRESENTATIONCAPS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGK_PRESENTATIONCAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_PRESENTATIONCAPS
---

# _DXGK_PRESENTATIONCAPS structure


## -description


The DXGK_PRESENTATIONCAPS structure identifies presentation capabilities of a display miniport driver that the driver provides through a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.


## -struct-fields




### -field NoScreenToScreenBlt

[in] A UINT value that specifies whether the display miniport driver can perform a bit-block transfer (bitblt) from the primary surface to the same primary surface. If <b>NoScreenToScreenBlt</b> is set, the driver cannot perform a screen-to-screen bit-block transfer. Therefore, the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) will not request the driver to perform such a bit-block transfer.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field NoOverlapScreenBlt

[in] A UINT value that specifies whether the display miniport driver can perform a bit-block transfer that overlaps. If <b>NoOverlapScreenBlt</b> is set, the driver cannot perform a bit-block transfer that overlaps. Therefore, the DirectX graphics kernel subsystem will not request the driver to perform such a bit-block transfer.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field SupportKernelModeCommandBuffer

 [in] A UINT value that specifies whether the display miniport driver supports GDI hardware-accelerated command buffer processing. If <b>SupportKernelModeCommandBuffer</b> is set, the driver can perform various hardware-accelerated bit-block transfer (bitblt) and fill operations when the DirectX graphics kernel subsystem calls the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a> function.

<div class="alert"><b>Note</b>    A display miniport driver should report that it supports GDI hardware acceleration only if the cache-coherent GPU aperture segment exists and there is no significant performance penalty when the CPU accesses the memory.</div>
<div> </div>
Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004). 

Supported starting with Windows 7.


### -field NoSameBitmapAlphaBlend

[in] A UINT value that specifies whether the display miniport driver can perform an alpha-blending operation when the source and destination allocations are the same. If <b>NoSameBitmapAlphaBlend</b> is set, the driver cannot perform such an operation and the DirectX graphics kernel subsystem will not request it.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008). 

Supported starting with Windows 7.


### -field NoSameBitmapStretchBlt

[in] A UINT value that specifies whether the display miniport driver can perform a stretch bit-block transfer operation when the source and destination allocations are the same. If <b>NoSameBitmapStretchBlt</b> is set, the driver cannot perform such an operation and the DirectX graphics kernel subsystem will not request it.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010). 

Supported starting with Windows 7.


### -field NoSameBitmapTransparentBlt

[in] A UINT value that specifies whether the display miniport driver can perform a transparent bit-block transfer operation when the source and destination allocations are the same. If <b>NoSameBitmapStretchBlt</b> is set, the driver cannot perform such an operation and the DirectX graphics kernel subsystem will not request it.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020). 

Supported starting with Windows 7.


### -field NoSameBitmapOverlappedAlphaBlend

[in] A UINT value that specifies whether the display miniport driver can perform an alpha-blending operation when the source and destination allocations are the same and source and destination rectangles overlap. If <b>NoSameBitmapOverlappedAlphaBlend</b> is set, the driver cannot perform such an operation and the DirectX graphics kernel subsystem will not request it.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040). 

Supported starting with Windows 7.


### -field NoSameBitmapOverlappedStretchBlt

[in] A UINT value that specifies whether the display miniport driver can perform a stretch bit-block transfer operation when the source and destination allocations are the same and source and destination rectangles overlap. If <b>NoSameBitmapOverlappedStretchBlt</b> is set, the driver cannot perform such an operation and the DirectX graphics kernel subsystem will not request it.

Setting this member is equivalent to setting the eight bit of the 32-bit <b>Value</b> member (0x00000080). 

Supported starting with Windows 7.


### -field DriverSupportsCddDwmInterop

[in] A UINT value that specifies whether the display miniport driver supports Canonical Display Driver (CDD) present operations to texture allocations that are created by the user-mode driver for the Desktop Windows Manager (DWM) to use. If <b>DriverSupportsCddDwmInterop</b> is set, the display miniport driver supports such present operations.

If the display miniport driver supports GDI hardware acceleration, <b>DriverSupportsCddDwmInterop</b> is ignored. In this case the driver must support present CDD operations to DWM texture allocations that are created by the user-mode driver.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100). 

Supported starting with Windows 7.


### -field Reserved0

[in] This member is reserved and should be set to zero.

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200). 

Supported starting with Windows 7.


### -field AlignmentShift

[in] A UINT value that specifies the minimum alignment value, in bytes, that the <b>XxxPitch</b> members of the DXGK_GDIARG_XXX structures require. <b>AlignmentShift</b> is given as a binary exponent. For example, to specify a required alignment value of 16 bytes, the display miniport driver should set <b>AlignmentShift</b> = 4. The minimum value is <b>AlignmentShift</b> = 2, which specifies a 4-byte alignment.

Setting this member is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400). 

Supported starting with Windows 7.


### -field MaxTextureWidthShift

[in] A UINT value that specifies the maximum texture width that the display miniport driver supports, which is computed as:

maximum supported texture width = 2 ^ (<b>MaxTextureWidthShift</b> + 11) texels.

For example, if <b>MaxTextureWidthShift</b> = 0, the maximum supported texture width is 2 ^ 11 = 2048.

Setting this member is equivalent to setting the twelfth bit of the 32-bit <b>Value</b> member (0x00000800). 

Supported starting with Windows 7.


### -field MaxTextureHeightShift

[in] A UINT value that specifies the maximum texture height that the display miniport driver supports, which is computed as:

maximum supported texture height = 2 ^ (<b>MaxTextureHeightShift</b> + 11) texels.

For example, if <b>MaxTextureHeightShift</b> = 0, the maximum supported texture height is 2 ^ 11 = 2048.

Setting this member is equivalent to setting the thirteenth bit of the 32-bit <b>Value</b> member (0x00001000). 

Supported starting with Windows 7.


### -field SupportAllBltRops

[in] A UINT value that specifies whether the display miniport driver supports all GDI ROP3 raster operations with solid color as a pattern in BitBlt and ColorFill commands. If <b>SupportAllBltRops</b> is set, the driver supports such raster operations.

Setting this member is equivalent to setting the fourteenth bit of the 32-bit <b>Value</b> member (0x00002000). 

Supported starting with Windows 7.


### -field SupportMirrorStretchBlt

[in] A UINT value that specifies whether the display miniport driver supports Stretch Blt operations (using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_stretchblt">DXGK_GDIARG_STRETCHBLT</a> structure) in mirror mode. If <b>SupportMirrorStretchBlt </b>is set, the driver supports such operations.

Setting this member is equivalent to setting the fifteenth bit of the 32-bit <b>Value</b> member (0x00004000). 

Supported starting with Windows 7.


### -field SupportMonoStretchBltModes

[in] A UINT value that specifies whether the display miniport driver supports Stretch Blt operations (using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gdiarg_stretchblt">DXGK_GDIARG_STRETCHBLT</a> structure) in BLACKONWHITE or WHITEONBLACK monochromatic rendering modes. If <b>SupportMonoStretchBltModes</b> is set, the driver supports such operations.

Setting this member is equivalent to setting the sixteenth bit of the 32-bit <b>Value</b> member (0x00008000). 

Supported starting with Windows 7.


### -field StagingRectStartPitchAligned

[in] A UINT value that specifies whether the display miniport driver requires the starting point (upper-left point) in the rectangle on a CPU-visible staging surface to be pitch-aligned, which means that the left coordinate is 0. If <b>AlignmentShift</b> is set, the upper-left point of the rectangle is pitch-aligned.

Setting this member is equivalent to setting the seventeenth bit of the 32-bit <b>Value</b> member (0x00010000). 

Supported starting with Windows 7.


### -field NoSameBitmapBitBlt

[in] A UINT value that specifies whether the display miniport driver can perform a bit-block transfer operation when the source and destination allocations are the same. If <b>NoSameBitmapBitBlt</b> is set, the driver cannot perform such an operation. Therefore, the DirectX graphics kernel subsystem will not request that the driver perform such an operation.

Setting this member is equivalent to setting the eighteenth bit of the 32-bit <b>Value</b> member (0x00020000). 

Supported starting with Windows 7.


### -field NoSameBitmapOverlappedBitBlt

[in] A UINT value that specifies whether the display miniport driver can perform a bit-block transfer operation when the source and destination allocations are the same and source and destination rectangles overlap. If <b>NoSameBitmapOverlappedBitBlt</b> is set, the driver cannot perform such an operation and the DirectX graphics kernel subsystem will not request it.

Setting this member is equivalent to setting the nineteenth bit of the 32-bit <b>Value</b> member (0x00040000). 

Supported starting with Windows 7.


### -field Reserved1

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the twentieth bit of the 32-bit <b>Value</b> member (0x00080000). 

Supported starting with Windows 7.


### -field NoTempSurfaceForClearTypeBlend

[in] A UINT value that specifies whether the driver needs a temporary surface during processing of commands that are specified by the <b>ClearTypeBlend</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_renderkm_command">DXGK_RENDERKM_COMMAND</a> structure. If <b>NoTempSurfaceForClearTypeBlend</b> is set, the driver does not need a temporary surface. In this case, the driver will use less video memory.

Setting this member to zero is equivalent to setting the twenty-first bit of the 32-bit <b>Value</b> member (0x00100000).

Supported starting with Windows 7.


### -field SupportSoftwareDeviceBitmaps

[in] This member is reserved and should be set to zero.

Setting this member is equivalent to setting the twenty-second bit of the 32-bit <b>Value</b> member (0x00200000).

Supported starting with Windows 8.


### -field NoCacheCoherentApertureMemory

[in] 

A UINT value that specifies that the driver does not support cache-coherent aperture memory.

Setting this member is equivalent to setting the twenty-third bit of the 32-bit <b>Value</b> member (0x00400000).

Supported starting with Windows 8.


### -field SupportLinearHeap

[in] The driver supports linear heap allocation from staging surfaces. 

Setting this member is equivalent to setting the twenty-fourth bit of the 32-bit <b>Value</b> member (0x00800000).

Supported starting with Windows 8.


### -field Reserved

[in] This member is reserved and should be set to zero.

Setting this member is equivalent to setting the twenty-fifth bit of the 32-bit <b>Value</b> member (0x01000000).

Supported starting with Windows 8.

[in] This member is reserved and should be set to zero.

Setting this member is equivalent to setting the twenty-fifth bit of the 32-bit <b>Value</b> member (0x02000000).

Supported starting with Windows 8.


### -field Value

A 32-bit value that identifies the driver's presentation capabilities.


## -remarks



A display miniport driver can specify presentation capabilities by setting bits in the 32-bit <b>Value</b> member or by setting individual members of the structure in the union that DXGK_PRESENTATIONCAPS contains.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_gdisurfacetype">D3DKMDT_GDISURFACETYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm">DxgkDdiRenderKm</a>
 

 

