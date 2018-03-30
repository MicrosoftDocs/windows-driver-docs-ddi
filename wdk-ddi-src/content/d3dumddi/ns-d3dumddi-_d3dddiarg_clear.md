---
UID: NS:d3dumddi._D3DDDIARG_CLEAR
title: "_D3DDDIARG_CLEAR"
author: windows-driver-content
description: The D3DDDIARG_CLEAR structure describes the parameters of a hardware-assisted clearing operation.
old-location: display\d3dddiarg_clear.htm
old-project: display
ms.assetid: f437f94c-075e-43e6-bf28-0e7c7bd78c5a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_CLEAR, D3DDDIARG_CLEAR structure [Display Devices], UMDisplayDriver_param_Structs_64efff84-8fe3-40d4-b823-27e4a235fd86.xml, _D3DDDIARG_CLEAR, d3dumddi/D3DDDIARG_CLEAR, display.d3dddiarg_clear
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_CLEAR
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CLEAR
---

# _D3DDDIARG_CLEAR structure


## -description


The D3DDDIARG_CLEAR structure describes the parameters of a hardware-assisted clearing operation. 


## -struct-fields




### -field Flags

[in] A UINT value that specifies which buffers the driver should clear and how the clear operation should be performed. This member can be a bitwise OR of the following values. For more information, see the Remarks section in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406339">Clear</a> reference page.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DCLEAR_TARGET (0x00000001l)

</td>
<td>
The driver should clear the context's render target to the color that is specified by the <b>FillColor</b> member. This value is defined in <i>D3d8types.h</i>.

</td>
</tr>
<tr>
<td>
D3DCLEAR_STENCIL (0x00000004l)

</td>
<td>
The driver should clear the context's stencil buffer to the value that is specified by the <b>FillStencil</b> member. This value is defined in <i>D3d8types.h</i>.

</td>
</tr>
<tr>
<td>
D3DCLEAR_ZBUFFER (0x00000002l)

</td>
<td>
The driver should clear the context's depth buffer to the depth that is specified by the <b>FillDepth</b> member. This value is defined in <i>D3d8types.h</i>.

</td>
</tr>
<tr>
<td>
D3DCLEAR_COMPUTERECTS (0x00000008l)

</td>
<td>
If rectangles are specified for clearing, the driver should clip them against the current viewport. If no rectangles are specified, the driver should clear the entire viewport. This value is defined in <i>D3dhal.h</i>.

</td>
</tr>
</table>
 


### -field FillColor

[in] The color value that the driver should clear the context's render target to.


### -field FillDepth

[in] The value that the driver should use to set the depth in the context's depth buffer. This member can be a value in the range from 0.0 through 1.0. 


### -field FillStencil

[in] The value that the driver should clear the context's stencil buffer to. This member can be an integer in the range from 0 through 2ⁿ-1, where <i>n</i> is the number of bits in the stencil buffer.


## -remarks



In a call to the user-mode display driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh406339">Clear</a> function, a pointer to a D3DDDIARG_CLEAR structure is passed in the <i>pData</i> parameter. The Microsoft Direct3D runtime passes information to the <i>NumRect</i> and <i>pRect</i> parameters in a call to the user-mode display driver's <b>Clear</b> function to specify the rectangular areas of the buffer that the driver should clear.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406339">Clear</a>
 

 

