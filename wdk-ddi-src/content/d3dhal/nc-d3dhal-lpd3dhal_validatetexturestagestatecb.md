---
UID: NC:d3dhal.LPD3DHAL_VALIDATETEXTURESTAGESTATECB
title: LPD3DHAL_VALIDATETEXTURESTAGESTATECB
author: windows-driver-content
description: The D3dValidateTextureStageState function returns the number of passes where the hardware can perform the blending operations specified in the current state.
old-location: display\d3dvalidatetexturestagestate.htm
old-project: display
ms.assetid: 6376842f-ebf5-43b0-81d8-fc5b15f595ab
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS, D3DTRANSFORMCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3dValidateTextureStageState
req.alt-loc: d3dhal.h
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
req.typenames: *LPD3DTRANSFORMCAPS, D3DTRANSFORMCAPS
---

# LPD3DHAL_VALIDATETEXTURESTAGESTATECB callback



## -description
The <b>D3dValidateTextureStageState</b> function returns the number of passes where the hardware can perform the blending operations specified in the current state.



## -prototype

````
LPD3DHAL_VALIDATETEXTURESTAGESTATECB D3dValidateTextureStageState;

DWORD APIENTRY D3dValidateTextureStageState(
  _In_ LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA pvtssd
)
{ ... }
````


## -parameters

### -param pvtssd [in]

Points to a <a href="..\d3dhal\ns-d3dhal-_d3dhal_validatetexturestagestatedata.md">D3DHAL_VALIDATETEXTURESTAGESTATEDATA</a> structure that contains the information required for the driver to determine and return the number of passes required to perform the blending operations.


## -returns
<b>D3dValidateTextureStageState</b> returns one of the following callback codes:
<dl>
<dt>
<a href="https://msdn.microsoft.com/da4cc7d7-6826-48aa-96c6-004e31fc3e3e">DDHAL_DRIVER_HANDLED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/da4cc7d7-6826-48aa-96c6-004e31fc3e3e">DDHAL_DRIVER_NOTHANDLED</a>
</dt>
</dl>

## -remarks
Microsoft Direct3D drivers that support texturing must implement <b>D3dValidateTextureStageState</b>.

The driver's implementation of this function must evaluate the current texture state for all texture stages associated with the context. If the driver's hardware can perform the specified blending operations, then the driver should return the number of passes on the state data that its hardware requires. If the hardware cannot perform the specified blending operations, then the driver should return one of the following error codes in the <b>ddrval</b> member of the D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure at <b>pvtssd</b>:

D3DERR_CONFLICTINGTEXTUREFILTER

The hardware cannot do both trilinear filtering and multitexturing at the same time.

D3DERR_TOOMANYOPERATIONS

The hardware cannot handle the specified number of operations.

D3DERR_UNSUPPORTEDALPHAARG

The hardware does not support a specified alpha argument.

D3DERR_UNSUPPORTEDALPHAOPERATION

The hardware does not support a specified alpha operation.

D3DERR_UNSUPPORTEDCOLORARG

The hardware does not support a specified color argument.

D3DERR_UNSUPPORTEDCOLOROPERATION

The hardware does not support a specified color operation.

D3DERR_UNSUPPORTEDFACTORVALUE

The hardware does not support a D3DTA_TFACTOR greater than 1.0.

D3DERR_WRONGTEXTUREFORMAT

The hardware does not support the current state in the selected texture format.

Direct3D calls <b>D3dValidateTextureStageState</b> in response to an application request through a call to <b>IDirect3DDevice7::ValidateDevice</b>. The number of passes returned by the driver is propagated back to the application, which can then decide whether it will proceed with rendering using the current state or if it must change the blending operations to render faster or to render at all. There are no limits to the number of passes that a driver can return.

A driver that returns more than one pass is responsible for properly executing the passes on all state and primitive data when rendering.


     Requests that are likely to fail <b>D3dValidateTextureStageState</b>:
    

Using diffuse iterated values as ARGs, or the BLENDDIFFUSE operation is sparsely supported on current hardware. Many parts can introduce only iterated color data at the last texture operation stage.

Trying to specify the texture for each stage as its arg1 in preference to arg2.

Attempting to use diffuse or scalar values at arbitrary multitexture blending stages. For many cards, these values can be used only at the final texture blending state; for others, only at the first stage.

Performing operations for the output alpha that are more intricate than, or substantially different from, the operations specified for the color channels is less likely to be supported.

Attempting to use D3DTA_TFACTOR and D3DTA_DIFFUSE simultaneously. Some hardware does not support this.

Attempting the simultaneous use of multiple textures and MIP mapped trilinear filtering. Many cards do not support these operations at the same time. If trilinear filtering has been requested for a texture involved in multitexture operations and it fails validation, turn off trilinear and try again. In this case, it may be best to do multipass rendering instead.


## -see-also
<dl>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_validatetexturestagestatedata.md">D3DHAL_VALIDATETEXTURESTAGESTATEDATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3dValidateTextureStageState callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

