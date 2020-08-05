---
UID: NS:d3dumddi._D3DDDIARG_SETLIGHT
title: _D3DDDIARG_SETLIGHT (d3dumddi.h)
description: The D3DDDIARG_SETLIGHT structure describes how to set light properties.
old-location: display\d3dddiarg_setlight.htm
tech.root: display
ms.assetid: 91da1c7a-aff5-4ece-b18d-14bd41e95464
ms.date: 05/10/2018
keywords: ["D3DDDIARG_SETLIGHT structure"]
ms.keywords: D3DDDIARG_SETLIGHT, D3DDDIARG_SETLIGHT structure [Display Devices], UMDisplayDriver_param_Structs_85eaa308-4edf-44ee-9235-e8637c10aa35.xml, _D3DDDIARG_SETLIGHT, d3dumddi/D3DDDIARG_SETLIGHT, display.d3dddiarg_setlight
f1_keywords:
 - "d3dumddi/D3DDDIARG_SETLIGHT"
 - "D3DDDIARG_SETLIGHT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_SETLIGHT
targetos: Windows
req.typenames: D3DDDIARG_SETLIGHT
---

# _D3DDDIARG_SETLIGHT structure


## -description


The D3DDDIARG_SETLIGHT structure describes how to set light properties. 


## -struct-fields




### -field Index

[in] An index into an array of lights.


### -field DataType

[in] A valid bitwise OR of the following flags that indicate the type of light data:

| **Value** | **Meaning** | 
|:--|:--|
| D3DDDISETLIGHT_DATA | Specifies that a pointer to a [D3DDDI_LIGHT](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_light) structure that defines light properties is supplied in the pLightProperties parameter in a call to the user-mode display driver's [SetLight](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setlight) function. | 
| D3DDDISETLIGHT_ENABLE | Enables the light whose index is specified in the Index member. | 
| D3DDDISETLIGHT_DISABLE | Disables the light whose index is specified in Index. | 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_light">D3DDDI_LIGHT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setlight">SetLight</a>
 

 

