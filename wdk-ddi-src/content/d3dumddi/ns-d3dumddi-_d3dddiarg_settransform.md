---
UID: NS:d3dumddi._D3DDDIARG_SETTRANSFORM
title: _D3DDDIARG_SETTRANSFORM (d3dumddi.h)
description: The D3DDDIARG_SETTRANSFORM structure describes how to set up a transform.
old-location: display\d3dddiarg_settransform.htm
tech.root: display
ms.assetid: 1bd5c22e-c4c1-4b0a-b5ed-76e17cbe1aee
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_SETTRANSFORM, D3DDDIARG_SETTRANSFORM structure [Display Devices], UMDisplayDriver_param_Structs_719de83f-0830-4b1a-aa72-e3f58553c733.xml, _D3DDDIARG_SETTRANSFORM, d3dumddi/D3DDDIARG_SETTRANSFORM, display.d3dddiarg_settransform
f1_keywords:
 - "d3dumddi/D3DDDIARG_SETTRANSFORM"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_SETTRANSFORM
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETTRANSFORM
---

# _D3DDDIARG_SETTRANSFORM structure


## -description


The D3DDDIARG_SETTRANSFORM structure describes how to set up a transform. 


## -struct-fields




### -field TransformType

[in] A D3DTRANSFORMSTATETYPE-typed value that indicates the type of transform to set up. This member can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| D3DTRANSFORMSTATE_PROJECTION | Projection transformation | 
| D3DTRANSFORMSTATE_VIEW | View transformation | 
| D3DTRANSFORMSTATE_WORLD | World transformation | 



### -field Matrix

[in] A D3DMATRIX structure that describes the matrix that is used to set up the transform. For more information about D3DMATRIX, see the Microsoft Windows SDK documentation.


## -remarks



The Microsoft Direct3D runtime uses D3DDDIARG_SETTRANSFORM in a call to the user-mode display driver <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_settransform">SetTransform</a> function to inform the driver about various hardware transformation and lighting matrices. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_settransform">SetTransform</a>
 

 

