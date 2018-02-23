---
UID: NS:d3dumddi._D3DDDIARG_MULTIPLYTRANSFORM
title: "_D3DDDIARG_MULTIPLYTRANSFORM"
author: windows-driver-content
description: The D3DDDIARG_MULTIPLYTRANSFORM structure describes how to modify the current transform.
old-location: display\d3dddiarg_multiplytransform.htm
old-project: display
ms.assetid: 4f14532f-8937-4715-aa9f-e38f18179af7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3DDDIARG_MULTIPLYTRANSFORM structure [Display Devices], UMDisplayDriver_param_Structs_9bae119f-aead-46d7-8a10-18cd6e227102.xml, d3dumddi/D3DDDIARG_MULTIPLYTRANSFORM, display.d3dddiarg_multiplytransform, _D3DDDIARG_MULTIPLYTRANSFORM, D3DDDIARG_MULTIPLYTRANSFORM
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
-	D3DDDIARG_MULTIPLYTRANSFORM
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_MULTIPLYTRANSFORM
---

# _D3DDDIARG_MULTIPLYTRANSFORM structure


## -description


The D3DDDIARG_MULTIPLYTRANSFORM structure describes how to modify the current transform. 


## -syntax


````
typedef struct _D3DDDIARG_MULTIPLYTRANSFORM {
  D3DTRANSFORMSTATETYPE TransformType;
  D3DMATRIX             Matrix;
} D3DDDIARG_MULTIPLYTRANSFORM;
````


## -struct-fields




### -field TransformType

[in] A D3DTRANSFORMSTATETYPE-typed value that indicates the type of the transform that is being modified. This member can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_PROJECTION

</td>
<td>
Projection transformation

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_VIEW

</td>
<td>
View transformation

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_WORLD

</td>
<td>
World transformation

</td>
</tr>
</table>
 


### -field Matrix

[in] A D3DMATRIX structure that describes the matrix that is used to modify the current transform. For more information about D3DMATRIX, see the Microsoft Windows SDK documentation.


## -remarks



The Microsoft Direct3D runtime uses D3DDDIARG_MULTIPLYTRANSFORM in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_multiplytransform.md">MultiplyTransform</a> function to inform the driver about modifications to the various transformation matrices.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_multiplytransform.md">MultiplyTransform</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_MULTIPLYTRANSFORM structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

