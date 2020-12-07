---
UID: NS:d3dumddi._DXVAHDDDI_VPCAPS
title: _DXVAHDDDI_VPCAPS (d3dumddi.h)
description: Describes a video processor and its capabilities.
old-location: display\dxvahdddi_vpcaps.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVAHDDDI_VPCAPS structure"]
ms.keywords: DXVA2_Structs_d3780f70-71f7-4105-a79e-df3abda62417.xml, DXVAHDDDI_VPCAPS, DXVAHDDDI_VPCAPS structure [Display Devices], _DXVAHDDDI_VPCAPS, d3dumddi/DXVAHDDDI_VPCAPS, display.dxvahdddi_vpcaps
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_VPCAPS is supported beginning with the Windows 7 operating system.
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
req.typenames: DXVAHDDDI_VPCAPS
f1_keywords:
 - _DXVAHDDDI_VPCAPS
 - d3dumddi/_DXVAHDDDI_VPCAPS
 - DXVAHDDDI_VPCAPS
 - d3dumddi/DXVAHDDDI_VPCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVAHDDDI_VPCAPS
---

# _DXVAHDDDI_VPCAPS structure


## -description

The <b>DXVAHDDDI_VPCAPS</b> structure describes a video processor and its capabilities.

## -struct-fields

### -field VPGuid

[out] A <b>GUID</b> that identifies the video processor.

### -field PastFrames

[out] The number of past reference frames that are required to perform the optimal video processing.

### -field FutureFrames

[out] The number of future reference frames that are required to perform the optimal video processing.

### -field ProcessorCaps

[out] A bitwise <b>OR</b> of the following values from the DXVAHDDDI_PROCESSOR_CAPS enumeration to indicate video processor-specific capabilities.

| **Value** | **Meaning** | 
|:--|:--|
| DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_BLEND (0x1) | The driver can perform blend deinterlacing where the two fields in an interlaced frame are blended. The driver uses this deinterlacing type when it deinterlaces at half rate. For more information about half rate, see [DXVAHDDDI_OUTPUT_RATE](./ne-d3dumddi-_dxvahdddi_output_rate.md). | 
| DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_BOB (0x2) | The driver can perform Bob deinterlacing where missing scan lines are created from the lines above and below the missing line. The 4tap filter ([–1,9,9,–1]/16) produces slightly better results. The driver uses this deinterlacing type when not enough reference frames are provided for adaptive deinterlacing. | 
| DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_ADAPTIVE (0x4) | The driver can perform adaptive deinterlacing where missing scan lines are created from either spatial or temporal interpolation by switching between the two interpolation types, depending on the pixel or field motion. |
| DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_MOTION_COMPENSATION (0x8) | The driver can perform motion-compensated deinterlacing where missing scan lines are created by using the motion vectors. This deinterlacing type is the most advanced deinterlacing that is implemented by using a proprietary algorithm. | 
| DXVAHDDDI_PROCESSOR_CAPS_INVERSE_TELECINE (0x10) | The driver can convert from the interlaced frames to original progressive frames by reversing the telecine. For more information about reversing the telecine, see the ITelecineCaps member. | 
| DXVAHDDDI_PROCESSOR_CAPS_FRAME_RATE_CONVERSION (0x20) | The driver can convert the frame rate by interpolating the frames. | 


The driver should not require any reference frames if it uses the deinterlacing types that are associated with DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_BLEND and DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_BOB.

When the driver uses inverse telecine with normal rate de-interlacing, because the telecined interlaced frames become fewer progressive frames, the driver maintains the frame rate by repeating the frames. If the same video processor supports the frame rate conversion, the driver might interpolate the frames rather than repeating while reversing the telecine. <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a> can control this interpolation.

For more information about blend and Bob de-interlacing, see <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a>.

### -field ITelecineCaps

[out] A bitwise <b>OR</b> of the following values from the DXVAHDDDI_ITELECINE_CAPS enumeration to indicate inverse telecine-specific capabilities.

| **Value** | **Meaning** | 
|:--|:--|
| DXVAHDDDI_ITELECINE_CAPS_32 (0x1) | The driver can perform reverse 3:2 telecine, NTSC(60i) -> Film(24p). | 
| DXVAHDDDI_ITELECINE_CAPS_22 (0x2) | The driver can perform reverse 2:2 telecine, PAL(50i) -> Film(25p:4% faster) and NTSC(60i) -> CG(30p). | 
| DXVAHDDDI_ITELECINE_CAPS_2224 (0x4) | The driver can perform reverse 2:2:2:4 telecine, NTSC(60i) -> DVCAM(24p). | 
| DXVAHDDDI_ITELECINE_CAPS_2332 (0x8) | The driver can perform reverse 2:3:3:2 telecine, NTSC(60i) -> DVCAM(24p). | 
| DXVAHDDDI_ITELECINE_CAPS_32322 (0x10) | The driver can perform reverse 3:2:3:2:2 telecine, NTSC(60i) -> Film(25p:4% faster). | 
| DXVAHDDDI_ITELECINE_CAPS_55 (0x20) | The driver can perform reverse 5:5 telecine, NTSC(60i) -> Animation(12p). | 
| DXVAHDDDI_ITELECINE_CAPS_64 (0x40) | The driver can perform reverse 6:4 telecine, NTSC(60i) -> Animation(12p). | 
| DXVAHDDDI_ITELECINE_CAPS_87 (0x80) | The driver can perform reverse 8:7 telecine, NTSC(60i) -> Anime(8p). | 
| DXVAHDDDI_ITELECINE_CAPS_222222222223 (0x100) | The driver can perform reverse 2:2:2:2:2:2:2:2:2:2:2:3 telecine, PAL(50i) -> Film(24p). | 
| DXVAHDDDI_ITELECINE_CAPS_OTHER (0x80000000) | The driver can perform reverse non-standard telecine. |

### -field CustomRateCount

[out] The number of supported custom output rates. The driver returns an array of <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_custom_rate_data">DXVAHDDDI_CUSTOM_RATE_DATA</a> structures for the custom output rates that the video processor supports when the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPCUSTOMRATES value set.

## -remarks

The user-mode display driver returns a pointer to a populated DXVAHDDDI_VPCAPS structure in the <b>pData</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a> structure when its <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPCAPS value set in the <b>Type</b> member of D3DDDIARG_GETCAPS.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_pool">D3DDDI_POOL</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_custom_rate_data">DXVAHDDDI_CUSTOM_RATE_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
