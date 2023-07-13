---
UID: NS:d3dkmthk._D3DKMT_CREATESTANDARDALLOCATION
title: D3DKMT_CREATESTANDARDALLOCATION (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATESTANDARDALLOCATION structure.
ms.date: 07/12/2023
keywords: ["D3DKMT_CREATESTANDARDALLOCATION structure"]
ms.keywords: D3DKMT_CREATESTANDARDALLOCATION, D3DKMT_CREATESTANDARDALLOCATION structure [Display Devices], _D3DKMT_CREATESTANDARDALLOCATION, d3dkmthk/D3DKMT_CREATESTANDARDALLOCATION, display.d3dkmt-createstandardallocation
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: D3DKMT_CREATESTANDARDALLOCATION
f1_keywords:
 - _D3DKMT_CREATESTANDARDALLOCATION
 - d3dkmthk/_D3DKMT_CREATESTANDARDALLOCATION
 - D3DKMT_CREATESTANDARDALLOCATION
 - d3dkmthk/D3DKMT_CREATESTANDARDALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CREATESTANDARDALLOCATION
 - D3DKMT_CREATESTANDARDALLOCATION
---

# D3DKMT_CREATESTANDARDALLOCATION structure

## -description

The **D3DKMT_CREATESTANDARDALLOCATION** structure is used to create a standard allocation.

## -struct-fields

### -field Type

A [**D3DKMT_STANDARDALLOCATIONTYPE**](ne-d3dkmthk-_d3dkmt_standardallocationtype.md) value that indicates the type of the standard allocation.

### -field ExistingHeapData

A [**D3DKMT_STANDARDALLOCATION_EXISTINGHEAP**](ns-d3dkmthk-_d3dkmt_standardallocation_existingheap.md) structure that holds information about the existing heap.

### -field Flags

A [**D3DKMT_CREATESTANDARDALLOCATIONFLAGS**](ns-d3dkmthk-_d3dkmt_createstandardallocationflags.md) structure that holds the flags to use to create a standard allocation.

## -see-also

[**D3DKMT_CREATEALLOCATION**](ns-d3dkmthk-_d3dkmt_createallocation.md)

[**D3DKMTCreateAllocation**](nf-d3dkmthk-d3dkmtcreateallocation.md)
