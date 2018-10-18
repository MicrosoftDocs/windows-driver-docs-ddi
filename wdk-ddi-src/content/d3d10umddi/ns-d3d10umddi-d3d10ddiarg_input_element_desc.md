---
UID: NS:d3d10umddi.D3D10DDIARG_INPUT_ELEMENT_DESC
title: D3D10DDIARG_INPUT_ELEMENT_DESC
author: windows-driver-content
description: The D3D10DDIARG_INPUT_ELEMENT_DESC structure describes an element of a layout.
old-location: display\d3d10ddiarg_input_element_desc.htm
ms.assetid: cc052b73-8837-4756-a192-620dcd5cacb5
ms.date: 5/10/2018
ms.keywords: D3D10DDIARG_INPUT_ELEMENT_DESC, D3D10DDIARG_INPUT_ELEMENT_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_c640f88f-3031-4412-a9bc-a8058cf8dab0.xml, d3d10umddi/D3D10DDIARG_INPUT_ELEMENT_DESC, display.d3d10ddiarg_input_element_desc
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	D3D10DDIARG_INPUT_ELEMENT_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_INPUT_ELEMENT_DESC
---

# D3D10DDIARG_INPUT_ELEMENT_DESC structure


## -description


The D3D10DDIARG_INPUT_ELEMENT_DESC structure describes an element of a layout.


## -struct-fields




### -field InputSlot

[in] The number of the input slot for the element. 


### -field AlignedByteOffset

[in] The aligned offset, in bytes, for the element. 


### -field Format

[in] A DXGI_FORMAT-typed value that indicates the format of the element.


### -field InputSlotClass

[in] A value that specifies the type of element. This member must be set to one of the following values from the D3D10_DDI_INPUT_CLASSIFICATION enumeration.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D10_DDI_INPUT_PER_VERTEX_DATA (0)

</td>
<td>
The <b>InstanceDataStepRate</b> member holds the number of instances to render.

</td>
</tr>
<tr>
<td>
D3D10_DDI_INPUT_PER_INSTANCE_DATA (1)

</td>
<td>
<b>InstanceDataStepRate</b> is set to zero.

</td>
</tr>
</table>
 


### -field InstanceDataStepRate

[in] The number of instances to render before incrementing to the next data element, if the <b>InputSlotClass</b> member is set to D3D10_DDI_INPUT_PER_INSTANCE_DATA. <b>InstanceDataStepRate</b> is set to zero if <b>InputSlotClass</b> is set to D3D10_DDI_INPUT_PER_VERTEX_DATA. 


### -field InputRegister

[in] The number of the input register for the element.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541674">D3D10DDIARG_CREATEELEMENTLAYOUT</a>
 

 

