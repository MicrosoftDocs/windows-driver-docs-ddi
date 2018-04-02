---
UID: NS:d3dumddi._DXVAHDDDI_VPCAPS
title: "_DXVAHDDDI_VPCAPS"
author: windows-driver-content
description: Describes a video processor and its capabilities.
old-location: display\dxvahdddi_vpcaps.htm
old-project: display
ms.assetid: 3e7e3280-3176-4bec-95ab-4dd203fce419
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_d3780f70-71f7-4105-a79e-df3abda62417.xml, DXVAHDDDI_VPCAPS, DXVAHDDDI_VPCAPS structure [Display Devices], _DXVAHDDDI_VPCAPS, d3dumddi/DXVAHDDDI_VPCAPS, display.dxvahdddi_vpcaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVAHDDDI_VPCAPS
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_VPCAPS
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

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_BLEND (0x1)

</td>
<td>
The driver can perform blend deinterlacing where the two fields in an interlaced frame are blended. The driver uses this deinterlacing type when it deinterlaces at half rate. For more information about half rate, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563061">DXVAHDDDI_OUTPUT_RATE</a>.

</td>
</tr>
<tr>
<td>
DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_BOB (0x2)

</td>
<td>
The driver can perform Bob deinterlacing where missing scan lines are created from the lines above and below the missing line. The 4tap filter ([–1,9,9,–1]/16) produces slightly better results. The driver uses this deinterlacing type when not enough reference frames are provided for adaptive deinterlacing.

</td>
</tr>
<tr>
<td>
DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_ADAPTIVE (0x4)

</td>
<td>
The driver can perform adaptive deinterlacing where missing scan lines are created from either spatial or temporal interpolation by switching between the two interpolation types, depending on the pixel or field motion. 

</td>
</tr>
<tr>
<td>
DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_MOTION_COMPENSATION (0x8)

</td>
<td>
The driver can perform motion-compensated deinterlacing where missing scan lines are created by using the motion vectors. This deinterlacing type is the most advanced deinterlacing that is implemented by using a proprietary algorithm.

</td>
</tr>
<tr>
<td>
DXVAHDDDI_PROCESSOR_CAPS_INVERSE_TELECINE (0x10)

</td>
<td>
The driver can convert from the interlaced frames to original progressive frames by reversing the telecine. For more information about reversing the telecine, see the <b>ITelecineCaps</b> member.

</td>
</tr>
<tr>
<td>
DXVAHDDDI_PROCESSOR_CAPS_FRAME_RATE_CONVERSION (0x20)

</td>
<td>
The driver can convert the frame rate by interpolating the frames.

</td>
</tr>
</table>
 

The driver should not require any reference frames if it uses the deinterlacing types that are associated with DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_BLEND and DXVAHDDDI_PROCESSOR_CAPS_DEINTERLACE_BOB.

When the driver uses inverse telecine with normal rate de-interlacing, because the telecined interlaced frames become fewer progressive frames, the driver maintains the frame rate by repeating the frames. If the same video processor supports the frame rate conversion, the driver might interpolate the frames rather than repeating while reversing the telecine. <a href="https://msdn.microsoft.com/library/windows/hardware/ff563092">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a> can control this interpolation.

For more information about blend and Bob de-interlacing, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563066">DXVAHDDDI_STREAM_DATA</a>. 


### -field ITelecineCaps

[out] A bitwise <b>OR</b> of the following values from the DXVAHDDDI_ITELECINE_CAPS enumeration to indicate inverse telecine-specific capabilities.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_32 (0x1)

</td>
<td>
The driver can perform reverse 3:2 telecine, NTSC(60i) -&gt; Film(24p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_22 (0x2)

</td>
<td>
The driver can perform reverse 2:2 telecine, PAL(50i) -&gt; Film(25p:4% faster) and NTSC(60i) -&gt; CG(30p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_2224 (0x4)

</td>
<td>
The driver can perform reverse 2:2:2:4 telecine, NTSC(60i) -&gt; DVCAM(24p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_2332 (0x8)

</td>
<td>
The driver can perform reverse 2:3:3:2 telecine, NTSC(60i) -&gt; DVCAM(24p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_32322 (0x10)

</td>
<td>
The driver can perform reverse 3:2:3:2:2 telecine, NTSC(60i) -&gt; Film(25p:4% faster).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_55 (0x20)

</td>
<td>
The driver can perform reverse 5:5 telecine, NTSC(60i) -&gt; Animation(12p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_64 (0x40)

</td>
<td>
The driver can perform reverse 6:4 telecine, NTSC(60i) -&gt; Animation(12p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_87 (0x80)

</td>
<td>
The driver can perform reverse 8:7 telecine, NTSC(60i) -&gt; Anime(8p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_222222222223 (0x100)

</td>
<td>
The driver can perform reverse 2:2:2:2:2:2:2:2:2:2:2:3 telecine, PAL(50i) -&gt; Film(24p).

</td>
</tr>
<tr>
<td>
DXVAHDDDI_ITELECINE_CAPS_OTHER (0x80000000)

</td>
<td>
The driver can perform reverse non-standard telecine.

</td>
</tr>
</table>
 


### -field CustomRateCount

[out] The number of supported custom output rates. The driver returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563045">DXVAHDDDI_CUSTOM_RATE_DATA</a> structures for the custom output rates that the video processor supports when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPCUSTOMRATES value set. 


## -remarks



The user-mode display driver returns a pointer to a populated DXVAHDDDI_VPCAPS structure in the <b>pData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a> structure when its <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPCAPS value set in the <b>Type</b> member of D3DDDIARG_GETCAPS.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544634">D3DDDI_POOL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563045">DXVAHDDDI_CUSTOM_RATE_DATA</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

