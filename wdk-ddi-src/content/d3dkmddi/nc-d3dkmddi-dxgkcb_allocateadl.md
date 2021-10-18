---
UID: NC:d3dkmddi.DXGKCB_ALLOCATEADL
tech.root: display
title: DXGKCB_ALLOCATEADL
ms.date: 10/13/2021
targetos: Windows
description: DxgkCbAllocateAdl creates an address descriptor list (ADL).
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
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

**DXGKCB_ALLOCATEADL** creates an address descriptor list (ADL).

## -parameters

### -param pArgs

[in/out] Pointer to a [**DXGKARGCB_ALLOCATE_ADL**](ns-d3dkmddi-dxgkargcb_allocate_adl.md) structure that contains information about the ADL to create. On success, returns a [**DXGK_ADL**](ns-d3dkmddi-dxgk_adl.md) structure with a list of page addresses that can be used to program the hardware.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code, such as STATUS_INVALID_PARAMETER.

## -remarks

The **DXGKCB_ALLOCATEADL** and [**DXGKCB_FREEADL**](nc-d3dkmddi-dxgkcb_freeadl.md) functions are used to create and destroy ADLs that describe memory addresses that can be programmed (mapped) to the GPU. The underlying memory can point to either logical or physical memory depending on whether the IOMMU is being used, so the driver must not attempt to assume that these addresses represent physical pages.

When an ADL is allocated from the physical object, *Dxgkrnl* guarantees that this memory remains locked and is non-pageable for the lifetime of the ADL.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_ALLOCATE_ADL**](ns-d3dkmddi-dxgkargcb_allocate_adl.md) and then call **DxgkCbAllocateAdl** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_ALLOCATE_ADL**](ns-d3dkmddi-dxgkargcb_allocate_adl.md)

[**DXGKCB_FREEADL**](nc-d3dkmddi-dxgkcb_freeadl.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
