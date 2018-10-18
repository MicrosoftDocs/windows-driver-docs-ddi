---
UID: NS:d3dumddi._D3DDDI_LIGHT
title: "_D3DDDI_LIGHT"
author: windows-driver-content
description: The D3DDDI_LIGHT structure describes a set of lighting properties.
old-location: display\d3dddi_light.htm
tech.root: display
ms.assetid: 53204334-bf91-46ad-93cc-84a4ec17ae54
ms.date: 5/10/2018
ms.keywords: D3DDDI_LIGHT, D3DDDI_LIGHT structure [Display Devices], D3D_other_Structs_4f43b697-886b-47bf-97b9-603306e899f8.xml, _D3DDDI_LIGHT, d3dumddi/D3DDDI_LIGHT, display.d3dddi_light
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
-	D3DDDI_LIGHT
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_LIGHT
---

# _D3DDDI_LIGHT structure


## -description


The D3DDDI_LIGHT structure describes a set of lighting properties. 


## -struct-fields




### -field Type

[in] A D3DLIGHTTYPE-typed value that indicates the type of the light source. For more information about D3DLIGHTTYPE, see the Microsoft Windows SDK documentation.


### -field Diffuse

[in] A D3DCOLORVALUE structure that indicates the diffuse color that is emitted by the light. For more information about D3DCOLORVALUE, see the Windows SDK documentation.


### -field Specular

[in] A D3DCOLORVALUE structure that indicates the specular color that is emitted by the light.


### -field Ambient

[in] A D3DCOLORVALUE structure that indicates the ambient color that is emitted by the light.


### -field Position

[in] A D3DVECTOR structure that indicates the position of the light in world space. This member has no meaning for directional lights (that is, if D3DLIGHT_DIRECTIONAL is set in the <b>Type</b> member) and is ignored in that situation. For more information about D3DVECTOR, see the Windows SDK documentation.


### -field Direction

[in] A D3DVECTOR structure that indicates the direction that the light is pointing in world space. This member has meaning only for directional lights and spotlights (that is, if D3DLIGHT_DIRECTIONAL and D3DLIGHT_SPOT are set in <b>Type</b>). This vector is not required to be normalized, but it should have a nonzero length.


### -field Range

[in] The distance beyond which the light has no effect. The maximum allowable value for this member is D3DLIGHT_RANGE_MAX, which is defined as the square root of FLT_MAX. This member does not affect directional lights.


### -field Falloff

[in] The decrease in illumination between a spotlight's inner cone (the angle that is specified by the <b>Theta</b> member) and the outer edge of the outer cone (the angle that is specified by the <b>Phi</b> member). The effect of falloff on the lighting is subtle. Furthermore, a small performance penalty is incurred by shaping the falloff curve. For these reasons, most developers set this member to 1.0.


### -field Attenuation0

[in] The light's constant attenuation factor. Attenuation values specify how the light intensity changes over distance. Attenuation does not affect directional lights. Valid values for this member range from 0.0 through infinity.


### -field Attenuation1

[in] The light's linear attenuation factor. Attenuation values specify how the light intensity changes over distance. Attenuation does not affect directional lights. Valid values for this member range from 0.0 through infinity.


### -field Attenuation2

[in] The light's quadratic attenuation factor. Attenuation values specify how the light intensity changes over distance. Attenuation does not affect directional lights. Valid values for this member range from 0.0 through infinity.


### -field Theta

[in] The angle, in radians, of a spotlight's inner cone--that is, the fully illuminated spotlight cone. This value must be in the range from 0 through the value that is specified by the <b>Phi</b> member.


### -field Phi

[in] The angle, in radians, that defines the outer edge of the spotlight's outer cone. Points outside this cone are not lit by the spotlight. This value must be between 0 and Pi.


## -see-also




<a href="https://msdn.microsoft.com/28e3992e-a636-47e2-a5a6-5da06d276b5c">SetLight</a>
 

 

