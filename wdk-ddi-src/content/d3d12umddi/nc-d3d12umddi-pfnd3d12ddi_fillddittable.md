---
UID: NC:d3d12umddi.PFND3D12DDI_FILLDDITTABLE
title: PFND3D12DDI_FILLDDITTABLE (d3d12umddi.h)
description: Learn more about the PFND3D12DDI_FILLDDITTABLE function.
ms.date: 09/29/2022
keywords: ["PFND3D12DDI_FILLDDITTABLE callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_FILLDDITTABLE
 - d3d12umddi/PFND3D12DDI_FILLDDITTABLE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_FILLDDITTABLE
dev_langs:
 - c++
---

# PFND3D12DDI_FILLDDITTABLE callback function

## -description

The **PFND3D12DDI_FILLDDITTABLE** callback function retrieves a list of function pointers implemented by the user-mode driver.

## -parameters

### -param unnamedParam1 [in]

**hAdapter** is the handle to the graphics adapter object.

### -param unnamedParam2 [in]

**tableType** is a [**D3D12DDI_TABLE_TYPE**](ne-d3d12umddi-d3d12ddi_table_type.md) value that indicates the type of function pointers to retrieve.

### -param unnamedParam3 [in/out]

**pTable** is a pointer to the returned table of callback functions that define the queried implementation.

### -param unnamedParam4 [in]

**tableSize** is the size of the table pointed to by **pTable**, in bytes.

### -param unnamedParam5 [in]

**tableNum** is the table index.

### -param unnamedParam6 [in, optional]

**hHandle** is a D3D12DDI_HRTTABLE handle.

## -returns

Returns an [**HRESULT**](/windows-hardware/drivers/debugger/hresult-values) value.

## -see-also

[**D3DDDI_ADAPTERFUNCS**](../d3dumddi/ns-d3dumddi-_d3dddi_adapterfuncs.md)

[**D3D12DDI_TABLE_TYPE**](ne-d3d12umddi-d3d12ddi_table_type.md)
