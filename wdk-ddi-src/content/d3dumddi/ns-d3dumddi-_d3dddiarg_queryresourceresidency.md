---
UID: NS:d3dumddi._D3DDDIARG_QUERYRESOURCERESIDENCY
title: _D3DDDIARG_QUERYRESOURCERESIDENCY (d3dumddi.h)
description: The D3DDDIARG_QUERYRESOURCERESIDENCY structure describes a list of resources on which residency is verified through the QueryResourceResidency function.
old-location: display\d3dddiarg_queryresourceresidency.htm
tech.root: display
ms.assetid: 14c0cb12-3ed0-4c78-befa-6da9e8cd7dbc
ms.date: 05/10/2018
keywords: ["D3DDDIARG_QUERYRESOURCERESIDENCY structure"]
ms.keywords: D3DDDIARG_QUERYRESOURCERESIDENCY, D3DDDIARG_QUERYRESOURCERESIDENCY structure [Display Devices], UMDisplayDriver_param_Structs_46a460d2-e511-43fd-9906-b9a47762f9a7.xml, _D3DDDIARG_QUERYRESOURCERESIDENCY, d3dumddi/D3DDDIARG_QUERYRESOURCERESIDENCY, display.d3dddiarg_queryresourceresidency
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
req.typenames: D3DDDIARG_QUERYRESOURCERESIDENCY
f1_keywords:
 - _D3DDDIARG_QUERYRESOURCERESIDENCY
 - d3dumddi/_D3DDDIARG_QUERYRESOURCERESIDENCY
 - D3DDDIARG_QUERYRESOURCERESIDENCY
 - d3dumddi/D3DDDIARG_QUERYRESOURCERESIDENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_QUERYRESOURCERESIDENCY
---

# _D3DDDIARG_QUERYRESOURCERESIDENCY structure


## -description

The D3DDDIARG_QUERYRESOURCERESIDENCY structure describes a list of resources on which residency is verified through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresourceresidency">QueryResourceResidency</a> function.

## -struct-fields

### -field pHandleList

[in] An array of handles to resources whose residency is queried. <b>pHandleList</b> cannot be <b>NULL</b>. A resource can be an object, which is derived from the <b>IDirect3DResource9</b> interface for a texture, volume texture, cube texture, vertex buffer, index buffer, or surface. For more information about <b>IDirect3DResource9</b>, see the DirectX SDK documentation.

### -field NumResources

[in] The number of resources in the array in the <b>pHandleList</b> member. The range is from 1 through 0xFFFFF.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresourceresidency">QueryResourceResidency</a>

