---
UID: NS:d3dumddi._D3DDDIARG_TEXTURESTAGESTATE
title: "_D3DDDIARG_TEXTURESTAGESTATE"
author: windows-driver-content
description: The D3DDDIARG_TEXTURESTAGESTATE structure describes how to update a texture at a particular stage in a multiple-texture group.
old-location: display\d3dddiarg_texturestagestate.htm
old-project: display
ms.assetid: 4810ec13-ec58-4ed6-ae4f-6690bd72cd8a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/D3DDDIARG_TEXTURESTAGESTATE, UMDisplayDriver_param_Structs_320d722f-2fbb-4fca-a06c-02e1be6e0190.xml, _D3DDDIARG_TEXTURESTAGESTATE, D3DDDIARG_TEXTURESTAGESTATE, display.d3dddiarg_texturestagestate, D3DDDIARG_TEXTURESTAGESTATE structure [Display Devices]
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
-	D3DDDIARG_TEXTURESTAGESTATE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_TEXTURESTAGESTATE
---

# _D3DDDIARG_TEXTURESTAGESTATE structure


## -description


The D3DDDIARG_TEXTURESTAGESTATE structure describes how to update a texture at a particular stage in a multiple-texture group. 


## -syntax


````
typedef struct _D3DDDIARG_TEXTURESTAGESTATE {
  UINT                        Stage;
  D3DDDITEXTURESTAGESTATETYPE State;
  UINT                        Value;
} D3DDDIARG_TEXTURESTAGESTATE;
````


## -struct-fields




### -field Stage

[in] The stage in a multiple-texture group that indicates the texture to be updated. This member can be an integer in the range from 0 through 7, with the highest numbered texture being closest to the frame buffer.


### -field State

[in] A D3DDDITEXTURESTAGESTATETYPE-typed value that indicates the texture state to be updated. 

Microsoft DirectX 9.0 and later applications can use values in the D3DSAMPLERSTATETYPE enumeration type to control the characteristics of sampler texture-related render states. In DirectX 8.0 and earlier, these sampler states were included in the D3DTEXTURESTAGESTATETYPE enumeration. The runtime maps sampler states (D3DSAMP_<i>Xxx</i>) to D3DDDITSS_<i>Xxx</i> values so that drivers are not required to process sampler states. For more information about D3DTEXTURESTAGESTATETYPE and D3DSAMPLERSTATETYPE, see the DirectX SDK documentation.

For a definition of each value, see the corresponding value of D3DTEXTURESTAGESTATETYPE or D3DSAMPLERSTATETYPE.

The following texture states are used exclusively by user-mode display drivers for texture colorkeying:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DDDITSS_DISABLETEXTURECOLORKEY (33)

</td>
<td>
Disable the current texture's colorkey. The <b>Value</b> member is set to <b>TRUE</b> to disable.

</td>
</tr>
<tr>
<td>
D3DDDITSS_TEXTURECOLORKEYVAL (34)

</td>
<td>
Update the colorkey for the current texture. The <b>Value</b> member is set to the colorkey value.

</td>
</tr>
</table> 


### -field Value

[in] The value to which the driver should update the texture state that is identified by the <b>Stage</b> and <b>State</b> members. For more information about values that can be updated for each texture state, see the definitions of the corresponding texture state in the D3DTEXTURESTAGESTATETYPE or D3DSAMPLERSTATETYPE enumeration type in the DirectX SDK documentation.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_settexturestagestate.md">SetTextureStageState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_TEXTURESTAGESTATE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

