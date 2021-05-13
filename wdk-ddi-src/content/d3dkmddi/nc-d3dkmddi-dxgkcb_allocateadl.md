---
UID: NC:d3dkmddi.DXGKCB_ALLOCATEADL
tech.root: display
title: DXGKCB_ALLOCATEADL
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: DxgkCbAllocateAdl creates an address descriptor list (ADL).
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ALLOCATEADL
f1_keywords:
 - DXGKCB_ALLOCATEADL
 - d3dkmddi/DXGKCB_ALLOCATEADL
dev_langs:
 - c++
---

## -description

**DxgkCbAllocateAdl** creates an address descriptor list (ADL).

## -parameters

### -param pArgs

Pointer to a [**DXGKARGCB_ALLOCATE_ADL**](ns-d3dkmddi-dxgkargcb_allocate_adl.md) structure that contains information about the ADL to create.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code, such as STATUS_INVALID_PARAMETER.

## -prototype

```cpp
//Declaration

DXGKCB_ALLOCATEADL DxgkCbAllocateAdl;

// Definition

NTSTATUS DxgkCbAllocateAdl(
    DXGKARGCB_ALLOCATE_ADL *pArgs
    );
{...}


```

## -remarks

The **DxgkCbAllocateAdl** and [**DxgkCbFreeAdl**](nc-d3dkmddi-dxgkcb_freeadl.md) functions are used to create and destroy address descriptor lists that describe memory addresses that can be programmed (mapped) to the GPU. The underlying memory can point to either logical or physical memory depending on whether the IOMMU is being used, so the driver must not attempt to assume that these addresses represent physical pages.

When an ADL is allocated from the physical object, *Dxgkrnl* guarantees that this memory remains locked and is non-pageable for the lifetime of the ADL.

## -see-also

[**DXGKARGCB_ALLOCATE_ADL**](ns-d3dkmddi-dxgkargcb_allocate_adl.md)

[**DxgkCbFreeAdl**](nc-d3dkmddi-dxgkcb_freeadl.md)
