---
UID: NS:d3dumddi._D3DDDIARG_MULTIPLYTRANSFORM
title: _D3DDDIARG_MULTIPLYTRANSFORM (d3dumddi.h)
description: The D3DDDIARG_MULTIPLYTRANSFORM structure describes how to modify the current transform.
old-location: display\d3dddiarg_multiplytransform.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_MULTIPLYTRANSFORM structure"]
ms.keywords: D3DDDIARG_MULTIPLYTRANSFORM, D3DDDIARG_MULTIPLYTRANSFORM structure [Display Devices], UMDisplayDriver_param_Structs_9bae119f-aead-46d7-8a10-18cd6e227102.xml, _D3DDDIARG_MULTIPLYTRANSFORM, d3dumddi/D3DDDIARG_MULTIPLYTRANSFORM, display.d3dddiarg_multiplytransform
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
req.typenames: D3DDDIARG_MULTIPLYTRANSFORM
f1_keywords:
 - _D3DDDIARG_MULTIPLYTRANSFORM
 - d3dumddi/_D3DDDIARG_MULTIPLYTRANSFORM
 - D3DDDIARG_MULTIPLYTRANSFORM
 - d3dumddi/D3DDDIARG_MULTIPLYTRANSFORM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_MULTIPLYTRANSFORM
 - D3DDDIARG_MULTIPLYTRANSFORM
---

# _D3DDDIARG_MULTIPLYTRANSFORM structure


## -description

The D3DDDIARG_MULTIPLYTRANSFORM structure describes how to modify the current transform.

## -struct-fields

### -field TransformType

[in] A D3DTRANSFORMSTATETYPE-typed value that indicates the type of the transform that is being modified. This member can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| D3DTRANSFORMSTATE_PROJECTION | Projection transformation | 
| D3DTRANSFORMSTATE_VIEW | View transformation | 
| D3DTRANSFORMSTATE_WORLD | World transformation |

### -field Matrix

[in] A D3DMATRIX structure that describes the matrix that is used to modify the current transform. For more information about D3DMATRIX, see the Microsoft Windows SDK documentation.

## -remarks

The Microsoft Direct3D runtime uses D3DDDIARG_MULTIPLYTRANSFORM in a call to the user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_multiplytransform">MultiplyTransform</a> function to inform the driver about modifications to the various transformation matrices.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_multiplytransform">MultiplyTransform</a>

