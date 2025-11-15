---
UID: NS:d3d12umddi.D3D12DDI_GENERIC_PROGRAM_DESC_0108
tech.root: display
title: D3D12DDI_GENERIC_PROGRAM_DESC_0108
ms.date: 11/14/2025
targetos: Windows
description: The D3D12DDI_GENERIC_PROGRAM_DESC_0108 structure describes a generic program state subobject that contains shader exports and associated configuration subobjects within a state object.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_GENERIC_PROGRAM_DESC_0108
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_GENERIC_PROGRAM_DESC_0108
f1_keywords:
 - D3D12DDI_GENERIC_PROGRAM_DESC_0108
 - d3d12umddi/D3D12DDI_GENERIC_PROGRAM_DESC_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_GENERIC_PROGRAM_DESC_0108
---

## -description

The **D3D12DDI_GENERIC_PROGRAM_DESC_0108** structure describes a generic program state subobject that contains shader exports and associated configuration subobjects within a state object. This structure defines the state subobject of type [**D3D12DDI_STATE_SUBOBJECT_TYPE_GENERIC_PROGRAM**](ne-d3d12umddi-d3d12ddi_state_subobject_type.md).

## -struct-fields

### -field ProgramName

A wide-character string that specifies the name of the generic program. This name is unique within the given state object and is used to identify the program.

### -field NumExports

The number of exports from the program. This value determines the number of elements in the **pExports** array. Can be 0 if the program doesn't export any shader functions.

### -field pExports

Pointer to an array of wide-character string pointers (LPCWSTR*), where each string specifies the name of an exported shader function from this program. Each export represents a shader function or entry point that can be referenced by other parts of the state object. Can be NULL if **NumExports** is 0.

### -field NumSubobjects

The number of subobjects associated with this generic program. This value determines the number of elements in the **pSubobjects** array. Can be 0 if the program doesn't have any associated subobjects.

### -field pSubobjects

Pointer to an array of pointers to [**D3D12DDI_STATE_SUBOBJECT_0054**](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md) structures. These subobjects provide additional configuration for the generic program, such as root signatures, local root signatures, or other state that applies to the program's exports. Can be NULL if **NumSubobjects** is 0.

## -remarks

A generic program is a collection of shader code with its exports and associated configuration subobjects within a state object. The runtime validates the generic program before passing this structure to the driver.

For more information, see [Generic programs](/windows-hardware/drivers/display/generic-programs).

## -see-also

[**D3D12DDI_EXPORT_DESC_0054**](ns-d3d12umddi-d3d12ddi_export_desc_0054.md)

[**D3D12DDI_STATE_SUBOBJECT_0054**](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md)

[**D3D12DDI_STATE_SUBOBJECT_TYPE**](ne-d3d12umddi-d3d12ddi_state_subobject_type.md)

[**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)

[**PFND3D12DDI_CREATE_STATE_OBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md)
