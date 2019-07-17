---
UID: NS:d3dkmddi._DXGK_PRESENTFLAGS
title: _DXGK_PRESENTFLAGS (d3dkmddi.h)
description: The DXGK_PRESENTFLAGS structure identifies, in bit-field flags, the type of present operation to perform.
old-location: display\dxgk_presentflags.htm
ms.assetid: ff1fe315-7824-4e61-83f5-6d75aba2a941
ms.date: 05/10/2018
ms.keywords: DXGK_PRESENTFLAGS, DXGK_PRESENTFLAGS structure [Display Devices], DmStructs_b8913202-bee3-4584-b323-6c6fb47a5c8d.xml, _DXGK_PRESENTFLAGS, d3dkmddi/DXGK_PRESENTFLAGS, display.dxgk_presentflags
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_PRESENTFLAGS"
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
- DXGK_PRESENTFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_PRESENTFLAGS
---

# _DXGK_PRESENTFLAGS structure


## -description


The DXGK_PRESENTFLAGS structure identifies, in bit-field flags, the type of present operation to perform.


## -struct-fields




### -field Blt

[in] A UINT value that specifies whether a copy operation, instead of a flip operation, occurs between source and destination surfaces.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field ColorFill

[in] A UINT value that specifies whether a source exists to present from. If this member is set, no source exists, and the driver should fill the destination rectangle on the destination surface with the A8R8G8B8 color that the <b>Color</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a> structure specifies.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Flip

[in] A UINT value that specifies whether a flip operation occurs between back and primary surfaces. If this member is set, the driver should perform the present operation by pointing the video scan output to the source rather than copying from the source to the destination. This type of present operation is tear-free.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field FlipWithNoWait

[in] A UINT value that specifies whether tear-free flip operations should not stall the graphics pipeline. If a tear-free flip stalls the graphics pipeline, the graphics processing unit (GPU) must wait for the tear-free flip to take effect before it runs the subsequent command. 

<b>FlipWithNoWait</b> can be set to <b>TRUE</b> (that is, 1) only if the display miniport driver set the <b>FlipOnVSyncWithNoWait</b> bit-field flag in the <b>FlipCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure when the DXGKQAITYPE_DRIVERCAPS value was specified in the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field SrcColorKey

[in] A UINT value that specifies whether to perform source color-keying by using the value in the <b>Color</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a> structure. That is, any pixel in the source surface that matches the color key should not be copied to the destination surface, and all of the source pixels that do not match the color key should be copied.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field DstColorKey

[in] A UINT value that specifies whether to perform destination color-keying by using the value in the <b>Color</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a> structure. That is, any pixel in the destination surface that matches the color key should be replaced with the corresponding pixel from the source surface, and all destination pixels that do not match the color key should not be replaced.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field LinearToSrgb

[in] A UINT value that specifies whether to convert the linear-formatted source to sRGB format during the copy operation. sRGB format is gamma corrected. For more information about the sRGB format, visit the <a href="https://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a> website.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field Rotate

[in] A UINT value that specifies whether to rotate the presentation data to match the current orientation of the screen during the presentation bit-block transfer (bitblt). The current orientation of the screen is set in the <b>Rotation</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure, which is set in the <b>ContentTransformation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure for the video present path.

The display miniport driver should rotate the data only if the <b>Rotate</b> bit-field flag is set. Even if the driver determines that the current orientation of the screen is rotated from the presentation data and <b>Rotate</b> is not set, the driver should not rotate the data.

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).


### -field FlipStereo

[in] Specifies whether the driver should flip both left and right images of a stereo allocation.

If the <b>FlipOnNextVSync</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure is  set, the driver should complete the flip to the left image on the next VSync and then complete the flip to the right image on the following VSync.

If the <b>FlipImmediate</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure is  set, the driver should immediately start to scan out from the new allocation. For example, if the driver was scanning a right image, it should start the new scan from the same relative offset in the right image of the new allocation.

The <b>FlipStereo</b> and <b>FlipStereoTemporaryMono</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    ninth bit of the 32-bit <b>Value</b> member (0x00000100).

Supported starting with Windows 8.


### -field FlipStereoTemporaryMono

[in] Specifies whether the driver should use the left image of a stereo allocation for the right and left portions of a stereo frame. The driver performs the same present operation as with <b>FlipStereo</b>, except that it should scan out only from the left image to produce both images of a stereo frame.

This member should  be set only if the driver reports support for this option in the current display mode by setting the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure to D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN.

The <b>FlipStereo</b> and <b>FlipStereoTemporaryMono</b> members cannot both be set at the same time.

The   <b>FlipStereoTemporaryMono</b> and <b>FlipStereoPreferRight</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    tenth bit of the 32-bit <b>Value</b> member (0x00000200).

Supported starting with Windows 8.


### -field FlipStereoPreferRight

[in] Specifies that when the driver clones a stereo primary allocation to a mono monitor, it should use the right image.

The   <b>FlipStereoTemporaryMono</b> and <b>FlipStereoPreferRight</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    eleventh bit of the 32-bit <b>Value</b> member (0x00000400).

Supported starting with Windows 8.


### -field BltStereoUseRight

[in] Specifies that when the driver presents from a stereo allocation to a mono allocation, it should use the right image. If not set, the driver should use the left image.

Setting this member is equivalent to setting the    twelfth bit of the 32-bit <b>Value</b> member (0x00000800).

Supported starting with Windows 8.


### -field FlipWithMultiPlaneOverlay

[in] Specifies whether a flip operation occurs between an overlay plane and the primary surface. If this member is set, the driver should perform the present operation by pointing the video scan output to the source plane rather than copying from the source plane to the destination.

Setting this member is equivalent to setting the    thirteenth bit of the 32-bit <b>Value</b> member (0x00001000).

Supported starting with Windows 8.1.


### -field RedirectedFlip

 


### -field Reserved

[in] This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 19 bits (0xFFFFE000) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.

[in] This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 24 bits (0xFFFFFF00) of the 32-bit <b>Value</b> member to zeros.


### -field Value

[in] A member in the union that DXGK_PRESENTFLAGS contains that can hold a 32-bit value that identifies the type of present operation to perform.


## -remarks



The <b>ColorFill</b>, <b>SrcColorKey</b>, and <b>DstColorKey</b> bit-field flags are mutually exclusive.

If any of the <b>FlipStereo</b>, <b>FlipStereoTemporaryMono</b>, or <b>FlipStereoPreferRight</b>  members are set, these conditions apply:

<ul>
<li>The <b>hAllocation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress">DXGKARG_SETVIDPNSOURCEADDRESS</a> structure should point to an allocation that is created with the <b>Stereo</b> member set in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_displaymode">D3DKMT_DISPLAYMODE</a> structure.</li>
<li>The <b>PrimarySegment</b> and <b>PrimaryAddress</b> members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress">DXGKARG_SETVIDPNSOURCEADDRESS</a> should point to the starting physical address of the allocation.</li>
<li>The driver should honor the settings of the <b>FlipImmediate</b> and <b>FlipOnNextVSync</b> members of  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure.</li>
</ul>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_displaymode">D3DKMT_DISPLAYMODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress">DXGKARG_SETVIDPNSOURCEADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>
 

 

