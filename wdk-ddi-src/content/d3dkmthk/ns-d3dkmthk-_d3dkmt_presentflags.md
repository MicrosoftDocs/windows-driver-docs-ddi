---
UID: NS:d3dkmthk._D3DKMT_PRESENTFLAGS
title: _D3DKMT_PRESENTFLAGS (d3dkmthk.h)
description: The D3DKMT_PRESENTFLAGS structure identifies how to perform a present operation.
old-location: display\d3dkmt_presentflags.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_PRESENTFLAGS structure"]
ms.keywords: D3DKMT_PRESENTFLAGS, D3DKMT_PRESENTFLAGS structure [Display Devices], OpenGL_Structs_bd28ba63-6019-4cc5-b1d0-7275a5a575b3.xml, _D3DKMT_PRESENTFLAGS, d3dkmthk/D3DKMT_PRESENTFLAGS, display.d3dkmt_presentflags
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_PRESENTFLAGS
f1_keywords:
 - _D3DKMT_PRESENTFLAGS
 - d3dkmthk/_D3DKMT_PRESENTFLAGS
 - D3DKMT_PRESENTFLAGS
 - d3dkmthk/D3DKMT_PRESENTFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_PRESENTFLAGS
---

# _D3DKMT_PRESENTFLAGS structure


## -description

The D3DKMT_PRESENTFLAGS structure identifies how to perform a present operation.

## -struct-fields

### -field Blt

A UINT value that specifies whether to bit-block transfer (bitblt) data to the primary surface. This bit-field flag can be used with the <b>DstRectValid</b> and <b>SrcRectValid</b> bit-field flags.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field ColorFill

A UINT value that specifies whether to perform a colorfill bitblt to the primary surface by using the value in the <b>Color</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a> structure. This bit-field flag can be used with the <b>DstRectValid</b> bit-field flag.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

### -field Flip

A UINT value that specifies whether to flip to a new surface.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

### -field FlipDoNotFlip

A UINT value that specifies whether to insert queued waits into the rendering stream. Setting this member indicates to flip to the same surface that is currently being scanned out.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).

### -field FlipDoNotWait

A UINT value that specifies whether the OpenGL installable client driver (ICD) requires that the present operation wait for the number of queued flip surfaces to fall below a particular limit before the operation begins. Setting this member indicates that the ICD does not require waiting. The default limit for the number of queued flip surfaces is three.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).

### -field FlipRestart

A UINT value that specifies whether to restart a flip to a new surface.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).

### -field DstRectValid

A UINT value that specifies whether the bitblt uses a destination rectangular area.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).

### -field SrcRectValid

A UINT value that specifies whether the bitblt uses a source rectangular area.

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).

### -field RestrictVidPnSource

A UINT value that specifies whether to restrict the bitblt. If the <b>hWindow</b> member is <b>NULL</b>, the <b>VidPnSourceId</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a> structure indicates which output the full-screen bitblt is directed to; if <b>hWindow</b> is non-<b>NULL</b>, <b>VidPnSourceId</b> indicates which output to restrict the windowed bitblt to.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).

### -field SrcColorKey

A UINT value that specifies whether to perform source color-keying by using the value in the <b>Color</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a> structure. That is, any pixel in the source surface that matches the color key should not be copied to the destination surface, and all of the source pixels that do not match the color key should be copied.

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).

### -field DstColorKey

A UINT value that specifies whether to perform destination color-keying by using the value in the <b>Color</b> member of D3DKMT_PRESENT. That is, any pixel in the destination surface that matches the color key should be replaced with the corresponding pixel from the source surface, and all of the destination pixels that do not match the color key should not be replaced. 

Setting this member is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400).

### -field LinearToSrgb

A UINT value that specifies whether to convert the linear-formatted source to sRGB format during the copy operation. sRGB format is gamma corrected. For more information about sRGB format, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a> website.

Setting this member is equivalent to setting the twelfth bit of the 32-bit <b>Value</b> member (0x00000800).

### -field PresentCountValid

A UINT value that specifies whether the value set in the <b>PresentCount</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a> structure is valid. 

Setting this member is equivalent to setting the thirteenth bit of the 32-bit <b>Value</b> member (0x00001000).

### -field Rotate

[in] A UINT value that specifies whether to rotate the presentation data to match the current orientation of the screen during the presentation bit-block transfer (bitblt). The current orientation of the screen is set in the <b>Rotation</b> member of a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure, which is set in the <b>ContentTransformation</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure for the video present path.

The display miniport driver should rotate the data only if the <b>Rotate</b> bit-field flag is set. Even if the driver determines that the current orientation of the screen is rotated from the presentation data and <b>Rotate</b> is not set, the driver should not rotate the data.

Setting this member is equivalent to setting the fourteenth bit of the 32-bit <b>Value</b> member (0x00002000).

### -field PresentToBitmap

A UINT value that specifies whether to present to a bitmap. 

Setting this member is equivalent to setting the fifteenth bit of the 32-bit <b>Value</b> member (0x00004000).

Supported starting with Windows 7.

### -field RedirectedFlip

A UINT value that specifies whether to redirect a flip to a new surface.

Setting this member is equivalent to setting the sixteenth bit of the 32-bit <b>Value</b> member (0x00008000).

Supported starting with Windows 7.

### -field RedirectedBlt

A UINT value that specifies whether to redirect a bitblt to a new surface. 

Setting this member is equivalent to setting the seventeenth bit of the 32-bit <b>Value</b> member (0x00010000).

Supported starting with Windows 7.

### -field FlipStereo

Specifies whether the driver should flip both left and right images of a stereo allocation.

If the <b>FlipOnNextVSync</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure is  set, the driver should complete the flip to the left image on the next VSync and then complete the flip to the right image on the following VSync.

If the <b>FlipImmediate</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure is  set, the driver should immediately start to scan out from the new allocation. For example, if the driver was scanning a right image, it should start the new scan from the same relative offset in the right image of the new allocation.

The <b>FlipStereo</b> and <b>FlipStereoTemporaryMono</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    eighteenth bit of the 32-bit <b>Value</b> member (0x00020000).

Supported starting with Windows 8.

### -field FlipStereoTemporaryMono

Specifies whether the driver should use the left image of a stereo allocation for the right and left portions of a stereo frame. The driver performs the same present operation as with <b>FlipStereo</b>, except that it should scan out only from the left image to produce both images of a stereo frame.

This member should  be set only if the driver reports support for this option in the current display mode by setting the <b>Type</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure to D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN.

The <b>FlipStereo</b> and <b>FlipStereoTemporaryMono</b> members cannot both be set at the same time.

The   <b>FlipStereoTemporaryMono</b> and <b>FlipStereoPreferRight</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    nineteenth bit of the 32-bit <b>Value</b> member (0x00040000).

Supported starting with Windows 8.

### -field FlipStereoPreferRight

Specifies that when the driver clones a stereo primary allocation to a mono monitor, it should use the right image.

The   <b>FlipStereoTemporaryMono</b> and <b>FlipStereoPreferRight</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    twentieth bit of the 32-bit <b>Value</b> member (0x00080000).

Supported starting with Windows 8.

### -field BltStereoUseRight

Specifies that when the driver presents from a stereo allocation to a mono allocation, it should use the right image. If not set, the driver should use the left image.

Setting this member is equivalent to setting the    twenty-first bit of the 32-bit <b>Value</b> member (0x00100000).

Supported starting with Windows 8.

### -field PresentHistoryTokenOnly

Specifies that the driver should submit only a present history token.

A <i>present history token</i> is a data packet that the rendering app submits to inform the Desktop Window Manager (DWM) that rendering is complete and the swap chain back buffer is ready to be presented.

Setting this member is equivalent to setting the    twenty-second bit of the 32-bit <b>Value</b> member (0x00200000).

Supported starting with Windows 8.

### -field PresentRegionsValid

Specifies that the <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a>.<b>pPresentRegions</b> member is a valid pointer (not <b>NULL</b>).

Setting this member is equivalent to setting the twenty-third    bit of the 32-bit <b>Value</b> member (0x00400000).

Supported starting with Windows 8.

### -field PresentDDA

This member is reserved and should be set to zero.

Setting this member is equivalent to setting the twenty-fourth    bit of the 32-bit <b>Value</b> member (0x00800000).

Supported starting with Windows 8.

### -field ProtectedContentBlankedOut

This member is reserved and should be set to zero.

Setting this member is equivalent to setting the    twenty-fifth bit of the 32-bit <b>Value</b> member (0x01000000).

Supported starting with Windows 8.

### -field RemoteSession

Specifies that the present operation is directed to a remote session.

Setting this member is equivalent to setting the    twenty-sixth bit of the 32-bit <b>Value</b> member (0x02000000).

Supported starting with Windows 8.

### -field CrossAdapter

 
The cross adapter.

### -field DurationValid

 
Indicates whether the duration is valid.

### -field PresentIndirect

Present indirect.

### -field PresentHMD

### -field Reserved

Supported starting with Windows 8.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 9 bits (0xFF800000) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A 32-bit value that identifies how to perform the present operation.

## -remarks

If any of the <b>FlipStereo</b>, <b>FlipStereoTemporaryMono</b>, or <b>FlipStereoPreferRight</b>  members are set, these conditions apply:

<ul>
<li>The <b>hAllocation</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress">DXGKARG_SETVIDPNSOURCEADDRESS</a> structure should point to an allocation that is created with the <b>Stereo</b> member set in the <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_displaymode">D3DKMT_DISPLAYMODE</a> structure.</li>
<li>The <b>PrimarySegment</b> and <b>PrimaryAddress</b> members of <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress">DXGKARG_SETVIDPNSOURCEADDRESS</a> should point to the starting physical address of the allocation.</li>
<li>The driver should honor the settings of the <b>FlipImmediate</b> and <b>FlipOnNextVSync</b> members of  the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure.</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_displaymode">D3DKMT_DISPLAYMODE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_present">D3DKMT_PRESENT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress">DXGKARG_SETVIDPNSOURCEADDRESS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a>
