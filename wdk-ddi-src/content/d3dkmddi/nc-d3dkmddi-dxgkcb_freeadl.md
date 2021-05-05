---
UID: NC:d3dkmddi.DXGKCB_FREEADL
tech.root: display
title: DXGKCB_FREEADL
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: DxgkCbFreeAdl destroys an address descriptor list (ADL) created in a prior call to DxgkCbAllocateAdl.
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
 - DXGKCB_FREEADL
f1_keywords:
 - DXGKCB_FREEADL
 - d3dkmddi/DXGKCB_FREEADL
dev_langs:
 - c++
---

## -description

**DxgkCbFreeAdl** destroys an address descriptor list (ADL) created in a prior call to [**DxgkCbAllocateAdl**](nc-d3dkmddi-dxgkcb_allocateadl.md).

## -parameters

### -param pArgs

Pointer to a [**DXGKARGCB_FREE_ADL**](ns-d3dkmddi-dxgkargcb_free_adl.md) structure that describes the ADL to destroy.

## -prototype

```cpp
//Declaration

DXGKCB_FREEADL DxgkCbFreeAdl;

// Definition

VOID DxgkCbFreeAdl(
    DXGKARGCB_FREE_ADL *pArgs
    );
{...}


```

## -remarks

The [**DxgkCbAllocateAdl**](nc-d3dkmddi-dxgkcb_allocateadl.md) and **DxgkCbFreeAdl** functions are used to create and destroy address descriptor lists that describe memory addresses that can be programmed to the GPU. The underlying memory can point to either logical or physical memory depending on whether the IOMMU is being used, so the driver must not attempt to assume that these addresses represent physical pages.

Once an ADL is freed, the memory referenced by that ADL must not be accessed by the GPU.

## -see-also

[**DXGKARGCB_FREE_ADL**](ns-d3dkmddi-dxgkargcb_free_adl.md)

[**DxgkCbAllocateAdl**](nc-d3dkmddi-dxgkcb_allocateadl.md)
