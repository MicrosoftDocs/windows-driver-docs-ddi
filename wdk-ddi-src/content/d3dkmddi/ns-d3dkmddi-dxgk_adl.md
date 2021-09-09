---
UID: NS:d3dkmddi._DXGK_ADL
tech.root: display
title: DXGK_ADL
ms.date: 05/13/2021
targetos: Windows
description: The DXGK_ADL structure is an address descriptor list (ADL), which is used to describe an array of pages that can be either physical or logical.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXGK_ADL
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_ADL
 - DXGK_ADL
f1_keywords:
 - _DXGK_ADL
 - d3dkmddi/_DXGK_ADL
 - DXGK_ADL
 - d3dkmddi/DXGK_ADL
dev_langs:
 - c++
---

## -description

The **DXGK_ADL** structure is an address descriptor list (ADL), which used to describe an array of pages that can be either physical or logical.

## -struct-fields

### -field PageCount

The number of pages that the ADL represents.

### -field Flags

A [**DXGK_ADL_FLAGS**](ns-d3dkmddi-dxgk_adl_flags.md) structure that specifies flags for the ADL.

### -field BasePageNumber

Used for contiguous ADLs. When **Flags.Contiguous** is set, **BasePageNumber** is the initial page number of a contiguous range of memory. An example of a contiguous ADL: if **PageCount**=3 and **BasePageNumber**=100, then the ADL represents the pages 100, 101, and 102 (address range 0x100000-0x102000).

### -field Pages

Used for non-contiguous ADLs. When **Flags.Contiguous** is not set, **Pages** points to an array of exactly **PageCount** pages. The pages in the array are not guaranteed to be contiguous.

**Pages** is of type **DXGK_PAGE_NUMBER**, which is guaranteed to be the same size as a [**PFN_NUMBER**](/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetmdlpfnarray). So this array can be substituted in place of an MDL's PFN array when programming the hardware.

## -remarks

*Dxgkernel* provides ADLs in order to support both physical and logical access modes, and be able to switch between the two modes seamlessly at runtime. An ADL is very similar to an MDL, but describes an array of pages that can be either physical or logical. Because these pages can be logical pages, the addresses described by an ADL cannot be mapped to a virtual address for direct CPU access.

## -see-also

[**DXGK_ADL_FLAGS**](ns-d3dkmddi-dxgk_adl_flags.md)
