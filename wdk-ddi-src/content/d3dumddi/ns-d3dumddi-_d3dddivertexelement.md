---
UID: NS:d3dumddi._D3DDDIVERTEXELEMENT
title: _D3DDDIVERTEXELEMENT (d3dumddi.h)
description: The D3DDDIVERTEXELEMENT structure describes an element in the array for a vertex shader declaration.
old-location: display\d3dddivertexelement.htm
tech.root: display
ms.assetid: acb0fc1d-e360-4cb9-9b3b-7d8d03146cfd
ms.date: 05/10/2018
keywords: ["_D3DDDIVERTEXELEMENT structure"]
ms.keywords: D3DDDIVERTEXELEMENT, D3DDDIVERTEXELEMENT structure [Display Devices], D3D_other_Structs_7f1e4f94-3964-4deb-b3b0-1b47f8953dfa.xml, _D3DDDIVERTEXELEMENT, d3dumddi/D3DDDIVERTEXELEMENT, display.d3dddivertexelement
f1_keywords:
 - "d3dumddi/D3DDDIVERTEXELEMENT"
 - "D3DDDIVERTEXELEMENT"
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
- D3DDDIVERTEXELEMENT
targetos: Windows
req.typenames: D3DDDIVERTEXELEMENT
---

# _D3DDDIVERTEXELEMENT structure


## -description


The D3DDDIVERTEXELEMENT structure describes an element in the array for a vertex shader declaration.


## -struct-fields




### -field Stream

[in] The number of the stream.


### -field Offset

[in] The offset (if any), in bytes, from the beginning of the stream to the start of the data.


### -field Type

[in] One of several predefined data types that define the data size. For more information about these types, see the D3DDECLTYPE enumeration type in the Microsoft Windows SDK documentation.


### -field Method

[in] The tessellator processing method. This method determines how the tessellator interprets and operates on the vertex data. For more information about these methods, see the D3DDECLMETHOD enumeration type in the Windows SDK documentation.


### -field Usage

[in] The intended use of the vertex data. For more information about the possible uses, see the D3DDECLUSAGE enumeration type in the Windows SDK documentation.


### -field UsageIndex

[in] A modification to the usage data that is specified in the <b>Usage</b> member. This modification enables multiple usage types to be specified.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createvertexshaderdecl">CreateVertexShaderDecl</a>
 

 

