---
UID: NS:d3dumddi._DDRAW_CAPS
title: "_DDRAW_CAPS"
author: windows-driver-content
description: The DDRAW_CAPS structure describes general Microsoft DirectDraw capabilities that the user-mode display driver supports.
old-location: display\ddraw_caps.htm
tech.root: display
ms.assetid: 023e3780-bc88-446b-b235-8853807fb05a
ms.date: 05/10/2018
ms.keywords: D3D_other_Structs_5e02fa0c-95ae-4b62-aaa3-7530aec9aee5.xml, DDRAW_CAPS, DDRAW_CAPS structure [Display Devices], _DDRAW_CAPS, d3dumddi/DDRAW_CAPS, display.ddraw_caps
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DDRAW_CAPS
product:
- Windows
targetos: Windows
req.typenames: DDRAW_CAPS
---

# _DDRAW_CAPS structure


## -description


The DDRAW_CAPS structure describes general Microsoft DirectDraw capabilities that the user-mode display driver supports.


## -struct-fields




### -field Caps

[out] A valid bitwise OR of the following general capability bits that the driver supports.

| **Capability bit** | **Meaning** | 
|:--|:--|
| DDRAW_CAPS_ZBLTS | Z-buffers can be used in bit-block transfer (bitblt) operations. | 
| DDRAW_CAPS_COLORKEY | Some form of color key can be used in either overlay or bitblt operations. For more specific color key capability information, see the CKeyCaps member. | 
| DDRAW_CAPS_BLTDEPTHFILL | Z-buffers can be depth-filled in bitblt operations. | 


### -field Caps2

[out] A valid bitwise OR of more of the following general capability bits that the driver supports.

| **Capability bit** | **Meaning** | 
|:--|:--|
| DDRAW_CAPS2_VIDEOPORT | A hardware video port can be used. | 
| DDRAW_CAPS2_CANDROPZ16BIT | Sixteen-bit RGBZ values can be converted into 16-bit RGB values. (The system does not support 8-bit conversions.) | 
| DDRAW_CAPS2_FLIPINTERVAL | The driver responds to the Flip bit-field flag. | 
| DDRAW_CAPS2_FLIPNOVSYNC | The driver responds to the FlipWithNoWait bit-field flag. | 
| DDRAW_CAPS2_DYNAMICTEXTURES | The driver supports dynamic textures. | 



### -field CKeyCaps

[out] A valid bitwise OR of the following color key capability bits that the driver supports.

| **Capability bit** | **Meaning** | 
|:--|:--|
| DDRAW_CKEYCAPS_SRCBLT | Transparent bit-block transfers can be performed with a color key that identifies bits of the source surface that are copied to the destination surface. | 
| DDRAW_CKEYCAPS_DESTBLT | Transparent bit-block transfers (bitblts) can be performed with a color key that identifies the replaceable bits of the destination surface. | 



### -field FxCaps

[out] A valid bitwise OR of the following stretching and effects capability bits that the driver supports.

| **Capability bit** | **Meaning** | 
|:--|:--|
| DDRAW_FXCAPS_BLTMIRRORLEFTRIGHT | Bit-block transfers (bitblts) that flip the contents of the source surface to the destination surface horizontally along the center axis can be performed. | 
| DDRAW_FXCAPS_BLTMIRRORUPDOWN | Bit-block transfers (bitblts) that flip the contents of the source surface to the destination surface vertically along the center axis can be performed. | 


### -field MaxVideoPorts

[out] The maximum number of video ports that the device supports.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

