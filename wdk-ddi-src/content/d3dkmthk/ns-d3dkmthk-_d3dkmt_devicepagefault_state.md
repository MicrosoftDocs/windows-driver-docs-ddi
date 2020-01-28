---
UID: NS:d3dkmthk._D3DKMT_DEVICEPAGEFAULT_STATE
title: _D3DKMT_DEVICEPAGEFAULT_STATE (d3dkmthk.h)
description: Contains information about the device page fault state.
ms.assetid: e2b07b4c-6826-4fde-8a6e-ad5647f5c4b8
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/_D3DKMT_DEVICEPAGEFAULT_STATE"
ms.keywords: _D3DKMT_DEVICEPAGEFAULT_STATE, D3DKMT_DEVICEPAGEFAULT_STATE, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_DEVICEPAGEFAULT_STATE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_DEVICEPAGEFAULT_STATE
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_DEVICEPAGEFAULT_STATE structure

## -description

Contains information about the device page fault state.

## -struct-fields

### -field FaultedPrimitiveAPISequenceNumber

Identifies the draw that caused the page fault (or DXGK_PRIMITIVE_API_SEQUENCE_NUMBER_UNKNOWN if such information is not available), when per draw fence write is enabled.

### -field FaultedPipelineStage

Renders pipeline stage during which the fault was generated, or DXGK_RENDER_PIPELINE_STAGE_UNKNOWN if such information is not available.

### -field FaultedBindTableEntry

A bind table index of a resource being accessed at the time of the fault, or DXGK_BIND_TABLE_ENTRY_UNKNOWN if such information is not available.

### -field PageFaultFlags

Flags that specifies the nature of the fault.

### -field FaultErrorCode

A structure that contains the error code describing the fault.

### -field FaultedVirtualAddress
 
The virtual address of faulting resource, or D3DGPU_NULL if such information is not available.

## -remarks

## -see-also
