---
UID: NS:d3dumddi._D3DDDIARG_SETMATERIAL
title: "_D3DDDIARG_SETMATERIAL"
author: windows-driver-content
description: The D3DDDIARG_SETMATERIAL structure describes the material properties that are used for rendering.
old-location: display\d3dddiarg_setmaterial.htm
old-project: display
ms.assetid: 66c35c60-9f6c-44d7-b6d5-9d50a3e33c2e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3DDDIARG_SETMATERIAL, UMDisplayDriver_param_Structs_5a3ecda9-5303-46f4-b7a2-42243e3a66d1.xml, d3dumddi/D3DDDIARG_SETMATERIAL, D3DDDIARG_SETMATERIAL structure [Display Devices], display.d3dddiarg_setmaterial, _D3DDDIARG_SETMATERIAL
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_SETMATERIAL
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETMATERIAL
---

# _D3DDDIARG_SETMATERIAL structure


## -description


The D3DDDIARG_SETMATERIAL structure describes the material properties that are used for rendering. 


## -syntax


````
typedef struct _D3DDDIARG_SETMATERIAL {
  D3DCOLORVALUE Diffuse;
  D3DCOLORVALUE Ambient;
  D3DCOLORVALUE Specular;
  D3DCOLORVALUE Emissive;
  FLOAT         Power;
} D3DDDIARG_SETMATERIAL;
````


## -struct-fields




### -field Diffuse

[in] A D3DCOLORVALUE structure that indicates the diffuse color of the material. For more information about D3DCOLORVALUE, see the Microsoft Windows SDK documentation.


### -field Ambient

[in] A D3DCOLORVALUE structure that indicates the ambient color of the material.


### -field Specular

[in] A D3DCOLORVALUE structure that indicates the specular color of the material.


### -field Emissive

[in] A D3DCOLORVALUE structure that indicates the emissive color of the material.


### -field Power

[in] A FLOAT value that indicates the sharpness of specular highlights. To turn off specular highlights for a material, set <b>Power</b> to 0 (setting <b>Specular</b> to 0 is not enough).


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmaterial.md">SetMaterial</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETMATERIAL structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

