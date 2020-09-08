---
UID: NS:d3dumddi._D3DDDIARG_TEXTURESTAGESTATE
title: _D3DDDIARG_TEXTURESTAGESTATE (d3dumddi.h)
description: The D3DDDIARG_TEXTURESTAGESTATE structure describes how to update a texture at a particular stage in a multiple-texture group.
old-location: display\d3dddiarg_texturestagestate.htm
tech.root: display
ms.assetid: 4810ec13-ec58-4ed6-ae4f-6690bd72cd8a
ms.date: 05/10/2018
keywords: ["D3DDDIARG_TEXTURESTAGESTATE structure"]
ms.keywords: D3DDDIARG_TEXTURESTAGESTATE, D3DDDIARG_TEXTURESTAGESTATE structure [Display Devices], UMDisplayDriver_param_Structs_320d722f-2fbb-4fca-a06c-02e1be6e0190.xml, _D3DDDIARG_TEXTURESTAGESTATE, d3dumddi/D3DDDIARG_TEXTURESTAGESTATE, display.d3dddiarg_texturestagestate
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
targetos: Windows
req.typenames: D3DDDIARG_TEXTURESTAGESTATE
f1_keywords:
 - _D3DDDIARG_TEXTURESTAGESTATE
 - d3dumddi/_D3DDDIARG_TEXTURESTAGESTATE
 - D3DDDIARG_TEXTURESTAGESTATE
 - d3dumddi/D3DDDIARG_TEXTURESTAGESTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_TEXTURESTAGESTATE
---

# _D3DDDIARG_TEXTURESTAGESTATE structure


## -description

The D3DDDIARG_TEXTURESTAGESTATE structure describes how to update a texture at a particular stage in a multiple-texture group.

## -struct-fields

### -field Stage

[in] The stage in a multiple-texture group that indicates the texture to be updated. This member can be an integer in the range from 0 through 7, with the highest numbered texture being closest to the frame buffer.

### -field State

[in] A D3DDDITEXTURESTAGESTATETYPE-typed value that indicates the texture state to be updated. 

Microsoft DirectX 9.0 and later applications can use values in the D3DSAMPLERSTATETYPE enumeration type to control the characteristics of sampler texture-related render states. In DirectX 8.0 and earlier, these sampler states were included in the D3DTEXTURESTAGESTATETYPE enumeration. The runtime maps sampler states (D3DSAMP_<i>Xxx</i>) to D3DDDITSS_<i>Xxx</i> values so that drivers are not required to process sampler states. For more information about D3DTEXTURESTAGESTATETYPE and D3DSAMPLERSTATETYPE, see the DirectX SDK documentation.

For a definition of each value, see the corresponding value of D3DTEXTURESTAGESTATETYPE or D3DSAMPLERSTATETYPE.

The following texture states are used exclusively by user-mode display drivers for texture colorkeying:

| **Value** | **Meaning** | 
|:--|:--|
| D3DDDITSS_DISABLETEXTURECOLORKEY (33) | Disable the current texture's colorkey. The Value member is set to TRUE to disable. | 
| D3DDDITSS_TEXTURECOLORKEYVAL (34) | Update the colorkey for the current texture. The Valuemember is set to the colorkey value. |

### -field Value

[in] The value to which the driver should update the texture state that is identified by the <b>Stage</b> and <b>State</b> members. For more information about values that can be updated for each texture state, see the definitions of the corresponding texture state in the D3DTEXTURESTAGESTATETYPE or D3DSAMPLERSTATETYPE enumeration type in the DirectX SDK documentation.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_settexturestagestate">SetTextureStageState</a>

