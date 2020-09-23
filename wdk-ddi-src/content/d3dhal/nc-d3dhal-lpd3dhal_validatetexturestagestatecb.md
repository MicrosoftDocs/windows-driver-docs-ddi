---
UID: NC:d3dhal.LPD3DHAL_VALIDATETEXTURESTAGESTATECB
title: LPD3DHAL_VALIDATETEXTURESTAGESTATECB (d3dhal.h)
description: The D3dValidateTextureStageState function returns the number of passes where the hardware can perform the blending operations specified in the current state.
old-location: display\d3dvalidatetexturestagestate.htm
tech.root: display
ms.assetid: 6376842f-ebf5-43b0-81d8-fc5b15f595ab
ms.date: 05/10/2018
keywords: ["LPD3DHAL_VALIDATETEXTURESTAGESTATECB callback function"]
ms.keywords: D3dValidateTextureStageState, D3dValidateTextureStageState callback, D3dValidateTextureStageState callback function [Display Devices], LPD3DHAL_VALIDATETEXTURESTAGESTATECB, d3dfncs_f83c205a-4cad-4365-beee-442a66e2c67a.xml, d3dhal/D3dValidateTextureStageState, display.d3dvalidatetexturestagestate
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.typenames: 
f1_keywords:
 - LPD3DHAL_VALIDATETEXTURESTAGESTATECB
 - d3dhal/LPD3DHAL_VALIDATETEXTURESTAGESTATECB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dhal.h
api_name:
 - D3dValidateTextureStageState
---

# LPD3DHAL_VALIDATETEXTURESTAGESTATECB callback function


## -description

The <b>D3dValidateTextureStageState</b> function returns the number of passes where the hardware can perform the blending operations specified in the current state.

## -parameters

### -param Arg1

*pvtssd* [in]

Points to a <a href="/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_validatetexturestagestatedata">D3DHAL_VALIDATETEXTURESTAGESTATEDATA</a> structure that contains the information required for the driver to determine and return the number of passes required to perform the blending operations.

## -returns

<b>D3dValidateTextureStageState</b> returns one of the following callback codes:

## -remarks

Microsoft Direct3D drivers that support texturing must implement <b>D3dValidateTextureStageState</b>.

The driver's implementation of this function must evaluate the current texture state for all texture stages associated with the context. If the driver's hardware can perform the specified blending operations, then the driver should return the number of passes on the state data that its hardware requires. If the hardware cannot perform the specified blending operations, then the driver should return one of the following error codes in the <b>ddrval</b> member of the D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure at <b>pvtssd</b>:

|Error Code|Meaning|
|--- |--- |
|D3DERR_CONFLICTINGTEXTUREFILTER|The hardware cannot do both trilinear filtering and multitexturing at the same time.|
|D3DERR_TOOMANYOPERATIONS|The hardware cannot handle the specified number of operations.|
|D3DERR_UNSUPPORTEDALPHAARG|The hardware does not support a specified alpha argument.|
|D3DERR_UNSUPPORTEDALPHAOPERATION|The hardware does not support a specified alpha operation.|
|D3DERR_UNSUPPORTEDCOLORARG|The hardware does not support a specified color argument.|
|D3DERR_UNSUPPORTEDCOLOROPERATION|The hardware does not support a specified color operation.|
|D3DERR_UNSUPPORTEDFACTORVALUE|The hardware does not support a D3DTA_TFACTOR greater than 1.0.|
|D3DERR_WRONGTEXTUREFORMAT|The hardware does not support the current state in the selected texture format.|

 

Direct3D calls <b>D3dValidateTextureStageState</b> in response to an application request through a call to <b>IDirect3DDevice7::ValidateDevice</b>. The number of passes returned by the driver is propagated back to the application, which can then decide whether it will proceed with rendering using the current state or if it must change the blending operations to render faster or to render at all. There are no limits to the number of passes that a driver can return.

A driver that returns more than one pass is responsible for properly executing the passes on all state and primitive data when rendering.

Requests that are likely to fail <b>D3dValidateTextureStageState</b>:

* Using diffuse iterated values as ARGs, or the BLENDDIFFUSE operation is sparsely supported on current hardware. Many parts can introduce only iterated color data at the last texture operation stage.

* Trying to specify the texture for each stage as its arg1 in preference to arg2.

* Attempting to use diffuse or scalar values at arbitrary multitexture blending stages. For many cards, these values can be used only at the final texture blending state; for others, only at the first stage.

* Attempting to do more in the first texture than merely replicate alpha to color channels or invert the input. For many cards, the blending units associated with the first texture are incapable of handling operations more complex than these. The samples below try to use only the second texture's blending unit, if it is possible to do so. The first unit is presumed to be in its default state in the samples.

     ```cpp
     dev.SetTextureStageState( n, D3DTSS_COLORARG1, D3DTA_TEXTURE );   *
     dev.SetTextureStageState( n, D3DTSS_COLOROP, D3DTOP_SELECTARG1 ); *
     ```

* Performing operations for the output alpha that are more intricate than, or substantially different from, the operations specified for the color channels is less likely to be supported.

* Attempting to use D3DTA_TFACTOR and D3DTA_DIFFUSE simultaneously. Some hardware does not support this.

* Attempting the simultaneous use of multiple textures and MIP mapped trilinear filtering. Many cards do not support these operations at the same time. If trilinear filtering has been requested for a texture involved in multitexture operations and it fails validation, turn off trilinear and try again. In this case, it may be best to do multipass rendering instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_validatetexturestagestatedata">D3DHAL_VALIDATETEXTURESTAGESTATEDATA</a>



<a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>