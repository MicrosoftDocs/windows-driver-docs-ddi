---
UID: NC:d3dumddi.PFND3DDDI_SETTEXTURESTAGESTATE
title: PFND3DDDI_SETTEXTURESTAGESTATE (d3dumddi.h)
description: The SetTextureStageState function updates the state of a texture at a particular stage in a multiple-texture group.
old-location: display\settexturestagestate.htm
tech.root: display
ms.assetid: 56b9d7bf-1036-4ad1-a0fb-4d7154b50b27
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETTEXTURESTAGESTATE, PFND3DDDI_SETTEXTURESTAGESTATE callback, SetTextureStageState, SetTextureStageState callback function [Display Devices], UserModeDisplayDriver_Functions_b84233ed-861a-4d59-a1b0-5b475f5019d5.xml, d3dumddi/SetTextureStageState, display.settexturestagestate
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetTextureStageState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETTEXTURESTAGESTATE callback function


## -description


The <i>SetTextureStageState</i> function updates the state of a texture at a particular stage in a multiple-texture group.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543389">D3DDDIARG_TEXTURESTAGESTATE</a> structure that describes how to update the texture.


## -returns



<i>SetTextureStageState</i> returns S_OK or an appropriate error result if the texture is not successfully updated.




## -remarks



The user-mode display driver is not required to store colorkey values in its private allocation structure because the Microsoft Direct3D runtime always passes the appropriate colorkeying information in calls to the driver's <i>SetTextureStageState</i> function. For example, the runtime passes the following colorkey information in the indicated members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543389">D3DDDIARG_TEXTURESTAGESTATE</a> structure that is pointed to by <i>pData</i> to perform the indicated colorkey operation: 

<ul>
<li>
D3DTSS_TEXTURECOLORKEYVAL in the <b>State</b> member and a colorkey value in the <b>Value</b> member to update the current texture's colorkey

</li>
<li>
D3DTSS_DISABLETEXTURECOLORKEY in the <b>State</b> member and <b>TRUE</b> in the <b>Value</b> member to disable the current texture's colorkey

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543389">D3DDDIARG_TEXTURESTAGESTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

