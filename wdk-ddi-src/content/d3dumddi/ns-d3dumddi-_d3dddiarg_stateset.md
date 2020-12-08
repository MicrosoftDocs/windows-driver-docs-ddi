---
UID: NS:d3dumddi._D3DDDIARG_STATESET
title: _D3DDDIARG_STATESET (d3dumddi.h)
description: The D3DDDIARG_STATESET structure describes how to set a state block.
old-location: display\d3dddiarg_stateset.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_STATESET structure"]
ms.keywords: D3DDDIARG_STATESET, D3DDDIARG_STATESET structure [Display Devices], UMDisplayDriver_param_Structs_926f9aca-1ecc-4086-88b7-0d07df9a05ae.xml, _D3DDDIARG_STATESET, d3dumddi/D3DDDIARG_STATESET, display.d3dddiarg_stateset
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
req.typenames: D3DDDIARG_STATESET
f1_keywords:
 - _D3DDDIARG_STATESET
 - d3dumddi/_D3DDDIARG_STATESET
 - D3DDDIARG_STATESET
 - d3dumddi/D3DDDIARG_STATESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_STATESET
---

# _D3DDDIARG_STATESET structure


## -description

The D3DDDIARG_STATESET structure describes how to set a state block.

## -struct-fields

### -field Operation

[in] The operation to perform, which can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| D3DHAL_STATESETBEGIN | Begin the state block that is referenced by the handle in the hStateSet member. | 
| D3DHAL_STATESETCAPTURE | Perform capture. When this flag is specified, the driver must capture a snapshot of the current state that matches the state block that is referenced by the handle in hStateSet. That is, only the state that is specified in the state block is captured. | 
| D3DHAL_STATESETCREATE | Create a state block of the type that is specified in the StateBlockType member. The information to record for each state block type is described in StateBlockType. | 
| D3DHAL_STATESETDELETE | Delete the state block that is referenced by the handle in hStateSet. | 
| D3DHAL_STATESETEND | End the state block that is referenced by the handle in hStateSet. | 
| D3DHAL_STATESETEXECUTE | Run the state block that is referenced by the handle in hStateSet. |

### -field StateBlockType

[in] A D3DSTATEBLOCKTYPE-typed value that indicates the type of state that the driver should record. This member can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| D3DSBT_ALL | The driver should capture all state.<br/>When requested to capture all state in pure device mode, the driver should capture all state with the exception of the current vertex stream state, the current index stream state, and the currently realized textures.<br/>The driver should capture (that is, record) the viewport, all of the world transforms, the view transform, the projection transform, the texture transform for all texture stages, all user-clip planes, the current material, all lights that have been used before the state block was created, the current vertex-shader handle, the current pixel-shader handle, the current vertex-shader constants, and the current pixel-shader constants. In addition, the driver should capture the following render and texture-stage states: D3DRENDERSTATE_SPECULARENABLE D3DRENDERSTATE_ZENABLE D3DRENDERSTATE_FILLMODE D3DRENDERSTATE_SHADEMODE D3DRENDERSTATE_LINEPATTERN D3DRENDERSTATE_ZWRITEENABLE D3DRENDERSTATE_ALPHATESTENABLE D3DRENDERSTATE_LASTPIXEL D3DRENDERSTATE_SRCBLEND D3DRENDERSTATE_DESTBLEND D3DRENDERSTATE_CULLMODE D3DRENDERSTATE_ZFUNC D3DRENDERSTATE_ALPHAREF D3DRENDERSTATE_ALPHAFUNC D3DRENDERSTATE_DITHERENABLE D3DRENDERSTATE_FOGENABLE D3DRENDERSTATE_STIPPLEDALPHA D3DRENDERSTATE_FOGCOLOR D3DRENDERSTATE_FOGTABLEMODE D3DRENDERSTATE_FOGSTART D3DRENDERSTATE_FOGEND D3DRENDERSTATE_FOGDENSITY D3DRENDERSTATE_EDGEANTIALIAS D3DRENDERSTATE_ALPHABLENDENABLE D3DRENDERSTATE_ZBIAS D3DRENDERSTATE_RANGEFOGENABLE D3DRENDERSTATE_STENCILENABLE D3DRENDERSTATE_STENCILFAIL D3DRENDERSTATE_STENCILZFAIL D3DRENDERSTATE_STENCILPASS D3DRENDERSTATE_STENCILFUNC D3DRENDERSTATE_STENCILREF D3DRENDERSTATE_STENCILMASK D3DRENDERSTATE_STENCILWRITEMASK D3DRENDERSTATE_TEXTUREFACTOR D3DRENDERSTATE_WRAP0 D3DRENDERSTATE_WRAP1 D3DRENDERSTATE_WRAP2 D3DRENDERSTATE_WRAP3 D3DRENDERSTATE_WRAP4 D3DRENDERSTATE_WRAP5 D3DRENDERSTATE_WRAP6 D3DRENDERSTATE_WRAP7 D3DRENDERSTATE_AMBIENT D3DRENDERSTATE_COLORVERTEX D3DRENDERSTATE_FOGVERTEXMODE D3DRENDERSTATE_CLIPPING D3DRENDERSTATE_LIGHTING D3DRENDERSTATE_NORMALIZENORMALS D3DRENDERSTATE_LOCALVIEWER D3DRENDERSTATE_EMISSIVEMATERIALSOURCE D3DRENDERSTATE_AMBIENTMATERIALSOURCE D3DRENDERSTATE_DIFFUSEMATERIALSOURCE D3DRENDERSTATE_SPECULARMATERIALSOURCE D3DRENDERSTATE_VERTEXBLEND D3DRENDERSTATE_CLIPPLANEENABLE D3DRS_SOFTWAREVERTEXPROCESSING D3DRS_POINTSIZE D3DRS_POINTSIZE_MIN D3DRS_POINTSPRITEENABLE D3DRS_POINTSCALEENABLE D3DRS_POINTSCALE_A D3DRS_POINTSCALE_B D3DRS_POINTSCALE_C D3DRS_MULTISAMPLEANTIALIAS D3DRS_MULTISAMPLEMASK D3DRS_PATCHEDGESTYLE D3DRS_PATCHSEGMENTS D3DRS_POINTSIZE_MAX D3DRS_INDEXEDVERTEXBLENDENABLE D3DRS_COLORWRITEENABLE D3DRS_TWEENFACTOR D3DRS_BLENDOP<br/>The driver should record the following texture-stage states:<br/>D3DTSS_COLOROP D3DTSS_COLORARG1 D3DTSS_COLORARG2 D3DTSS_ALPHAOP D3DTSS_ALPHAARG1 D3DTSS_ALPHAARG2 D3DTSS_BUMPENVMAT00 D3DTSS_BUMPENVMAT01 D3DTSS_BUMPENVMAT10 D3DTSS_BUMPENVMAT11 D3DTSS_TEXCOORDINDEX D3DTSS_ADDRESSU D3DTSS_ADDRESSV D3DTSS_BORDERCOLOR D3DTSS_MAGFILTER D3DTSS_MINFILTER D3DTSS_MIPFILTER D3DTSS_MIPMAPLODBIAS D3DTSS_MAXMIPLEVEL D3DTSS_MAXANISOTROPY D3DTSS_BUMPENVLSCALE D3DTSS_BUMPENVLOFFSET D3DTSS_TEXTURETRANSFORMFLAGS D3DTSS_ADDRESSW D3DTSS_COLORARG0 D3DTSS_ALPHAARG0 D3DTSS_RESULTARG | 
| D3DSBT_PIXELSTATE | The driver should capture only pixel state.<br/>When capturing pixel state in pure device mode, the driver should capture (that is, record) the current pixel shader handle, the current pixel shader constants, and the following pixel processing-related render states and texture stage states:<br/>D3DRENDERSTATE_ZENABLE D3DRENDERSTATE_FILLMODE D3DRENDERSTATE_SHADEMODE D3DRENDERSTATE_LINEPATTERN D3DRENDERSTATE_ZWRITEENABLE D3DRENDERSTATE_ALPHATESTENABLE D3DRENDERSTATE_LASTPIXEL D3DRENDERSTATE_SRCBLEND D3DRENDERSTATE_DESTBLEND D3DRENDERSTATE_ZFUNC D3DRENDERSTATE_ALPHAREF D3DRENDERSTATE_ALPHAFUNC D3DRENDERSTATE_DITHERENABLE D3DRENDERSTATE_STIPPLEDALPHA D3DRENDERSTATE_FOGSTART D3DRENDERSTATE_FOGEND D3DRENDERSTATE_FOGDENSITY D3DRENDERSTATE_EDGEANTIALIAS D3DRENDERSTATE_ALPHABLENDENABLE D3DRENDERSTATE_ZBIAS D3DRENDERSTATE_STENCILENABLE D3DRENDERSTATE_STENCILFAIL D3DRENDERSTATE_STENCILZFAIL D3DRENDERSTATE_STENCILPASS D3DRENDERSTATE_STENCILFUNC D3DRENDERSTATE_STENCILREF D3DRENDERSTATE_STENCILMASK D3DRENDERSTATE_STENCILWRITEMASK D3DRENDERSTATE_TEXTUREFACTOR D3DRENDERSTATE_WRAP0 D3DRENDERSTATE_WRAP1 D3DRENDERSTATE_WRAP2 D3DRENDERSTATE_WRAP3 D3DRENDERSTATE_WRAP4 D3DRENDERSTATE_WRAP5 D3DRENDERSTATE_WRAP6 D3DRENDERSTATE_WRAP7 D3DRS_COLORWRITEENABLE D3DRS_BLENDOP D3DTSS_COLOROP D3DTSS_COLORARG1 D3DTSS_COLORARG2 D3DTSS_ALPHAOP D3DTSS_ALPHAARG1 D3DTSS_ALPHAARG2 D3DTSS_BUMPENVMAT00 D3DTSS_BUMPENVMAT01 D3DTSS_BUMPENVMAT10 D3DTSS_BUMPENVMAT11 D3DTSS_TEXCOORDINDEX D3DTSS_ADDRESSU D3DTSS_ADDRESSV D3DTSS_BORDERCOLOR D3DTSS_MAGFILTER D3DTSS_MINFILTER D3DTSS_MIPFILTER D3DTSS_MIPMAPLODBIAS D3DTSS_MAXMIPLEVEL D3DTSS_MAXANISOTROPY D3DTSS_BUMPENVLSCALE D3DTSS_BUMPENVLOFFSET D3DTSS_TEXTURETRANSFORMFLAGS D3DTSS_ADDRESSW D3DTSS_COLORARG0 D3DTSS_ALPHAARG0 D3DTSS_RESULTARG | 
| D3DSBT_VERTEXSTATE | The driver should capture only vertex state.<br/>When capturing vertex state in pure device mode, the driver should capture (record) all lights that have been used before the state block was created, the current vertex shader handle, the current vertex shader constants, and the following vertex processing-related render states and texture stage states:<br/>D3DRENDERSTATE_SHADEMODE D3DRENDERSTATE_SPECULARENABLE D3DRENDERSTATE_CULLMODE D3DRENDERSTATE_FOGENABLE D3DRENDERSTATE_FOGCOLOR D3DRENDERSTATE_FOGTABLEMODE D3DRENDERSTATE_FOGSTART D3DRENDERSTATE_FOGEND D3DRENDERSTATE_FOGDENSITY D3DRENDERSTATE_RANGEFOGENABLE D3DRENDERSTATE_AMBIENT D3DRENDERSTATE_COLORVERTEX D3DRENDERSTATE_FOGVERTEXMODE D3DRENDERSTATE_CLIPPING D3DRENDERSTATE_LIGHTING D3DRENDERSTATE_NORMALIZENORMALS D3DRENDERSTATE_LOCALVIEWER D3DRENDERSTATE_EMISSIVEMATERIALSOURCE D3DRENDERSTATE_AMBIENTMATERIALSOURCE D3DRENDERSTATE_DIFFUSEMATERIALSOURCE D3DRENDERSTATE_SPECULARMATERIALSOURCE D3DRENDERSTATE_VERTEXBLEND D3DRENDERSTATE_CLIPPLANEENABLE D3DRS_SOFTWAREVERTEXPROCESSING D3DRS_POINTSIZE D3DRS_POINTSIZE_MIN D3DRS_POINTSPRITEENABLE D3DRS_POINTSCALEENABLE D3DRS_POINTSCALE_A D3DRS_POINTSCALE_B D3DRS_POINTSCALE_C D3DRS_MULTISAMPLEANTIALIAS D3DRS_MULTISAMPLEMASK D3DRS_PATCHEDGESTYLE D3DRS_PATCHSEGMENTS D3DRS_POINTSIZE_MAX D3DRS_INDEXEDVERTEXBLENDENABLE D3DRS_TWEENFACTOR D3DTSS_TEXCOORDINDEX D3DTSS_TEXTURETRANSFORMFLAGS | 
| NULL | No predefined state group is specified. |

### -field hStateSet

[in/out] A handle to the state block that is manipulated by the operation that is specified in the <b>Operation</b> member.

A state-block handle is passed in a call to the user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_stateset">StateSet</a> function when <b>Operation</b> is set to D3DHAL_STATESETEXECUTE.

The <i>StateSet</i> function returns the state-block handle when <b>Operation</b> is set to D3DHAL_STATESETBEGIN and D3DHAL_STATESETCREATE.

## -remarks

If the user-mode display driver implements extended render states (that is, render states beyond those that the Microsoft Direct3D runtime supplies), the driver uses the <b>StateBlockType</b> member to determine the type of predefined render state that is being used. From this information, the driver can determine how to append the state block appropriately to support its extensions. 

The <b>StateBlockType</b> member is valid only for D3DHAL_STATESETBEGIN, D3DHAL_STATESETEND, and D3DHAL_STATECREATE operations. For more information about the D3DSTATEBLOCKTYPE enumeration type, see the Microsoft Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_stateset">StateSet</a>
