---
UID: NS:d3dkmthk._D3DKMT_SEGMENTGROUPSIZEINFO
title: D3DKMT_SEGMENTGROUPSIZEINFO (d3dkmthk.h)
description: Learn more about the D3DKMT_SEGMENTGROUPSIZEINFO structure.
ms.date: 02/06/2025
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
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
tech.root: display
req.typenames: D3DKMT_SEGMENTGROUPSIZEINFO
f1_keywords:
 - _D3DKMT_SEGMENTGROUPSIZEINFO
 - d3dkmthk/_D3DKMT_SEGMENTGROUPSIZEINFO
 - D3DKMT_SEGMENTGROUPSIZEINFO
 - d3dkmthk/D3DKMT_SEGMENTGROUPSIZEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_SEGMENTGROUPSIZEINFO
 - D3DKMT_SEGMENTGROUPSIZEINFO
---

# D3DKMT_SEGMENTGROUPSIZEINFO structure

## -description

The **D3DKMT_SEGMENTGROUPSIZEINFO** structure holds information about the segment group size.

## -struct-fields

### -field PhysicalAdapterIndex

The physical adapter index in the LDA (linked display adapter) chain.

### -field LegacyInfo

A [**D3DKMT_SEGMENTSIZEINFO**](ns-d3dkmthk-_d3dkmt_segmentsizeinfo.md) structure that holds legacy segment size info.

### -field LocalMemory

Size of the local memory, in bytes.

### -field NonLocalMemory

Size of non-local memory, in bytes.

### -field NonBudgetMemory

Size of [non-budget memory](/windows-hardware/drivers/display/process-residency-budgets).

## -see-also

[**D3DKMT_SEGMENTSIZEINFO**](ns-d3dkmthk-_d3dkmt_segmentsizeinfo.md)

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
