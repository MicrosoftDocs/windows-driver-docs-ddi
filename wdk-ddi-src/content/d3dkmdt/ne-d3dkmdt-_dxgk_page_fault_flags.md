---
UID: NE:d3dkmdt._DXGK_PAGE_FAULT_FLAGS
title: _DXGK_PAGE_FAULT_FLAGS (d3dkmdt.h)
description: DXGK_PAGE_FAULT_FLAGS enumeration describes the nature of the page fault that has occurred and the prescribed OS recovery action.
old-location: display\dxgk_page_fault_flags.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGK_PAGE_FAULT_FLAGS enumeration"]
ms.keywords: DXGK_PAGE_FAULT_ADAPTER_RESET_REQUIRED, DXGK_PAGE_FAULT_ENGINE_RESET_REQUIRED, DXGK_PAGE_FAULT_FATAL_HARDWARE_ERROR, DXGK_PAGE_FAULT_FENCE_INVALID, DXGK_PAGE_FAULT_FLAGS, DXGK_PAGE_FAULT_FLAGS enumeration [Display Devices], DXGK_PAGE_FAULT_IOMMU, DXGK_PAGE_FAULT_WRITE, _DXGK_PAGE_FAULT_FLAGS, d3dkmdt/DXGK_PAGE_FAULT_ADAPTER_RESET_REQUIRED, d3dkmdt/DXGK_PAGE_FAULT_ENGINE_RESET_REQUIRED, d3dkmdt/DXGK_PAGE_FAULT_FATAL_HARDWARE_ERROR, d3dkmdt/DXGK_PAGE_FAULT_FENCE_INVALID, d3dkmdt/DXGK_PAGE_FAULT_FLAGS, d3dkmdt/DXGK_PAGE_FAULT_IOMMU, d3dkmdt/DXGK_PAGE_FAULT_WRITE, display.dxgk_page_fault_flags
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: DXGK_PAGE_FAULT_FLAGS
f1_keywords:
 - _DXGK_PAGE_FAULT_FLAGS
 - d3dkmdt/_DXGK_PAGE_FAULT_FLAGS
 - DXGK_PAGE_FAULT_FLAGS
 - d3dkmdt/DXGK_PAGE_FAULT_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmdt.h
api_name:
 - DXGK_PAGE_FAULT_FLAGS
---

# _DXGK_PAGE_FAULT_FLAGS enumeration


## -description

<b>DXGK_PAGE_FAULT_FLAGS</b> enumeration describes the nature of the page fault that has occurred and the prescribed OS recovery action.

## -enum-fields

### -field DXGK_PAGE_FAULT_WRITE

When set, this indicates that the faulted GPU virtual operation was a write operation.

### -field DXGK_PAGE_FAULT_FENCE_INVALID

When set, this indicates that a faulting packet could not be determined. In this case, the OS will have to perform a GPU reset action to clear the GPU error state, and one of the subsequent bits will have to be set.

When not set, this indicates that the DMA packet submitted with <b>FaultedFenceId</b> (in the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure) was the cause of the fault. Similar to how the preemption and completion fences are handled, the OS will treat all pending packets with fence IDs less than <b>FaultedFenceId</b> as completed, and the driver will be required to advance its notion of the completed fence ID to <b>FaultedFenceId</b>.

### -field DXGK_PAGE_FAULT_ADAPTER_RESET_REQUIRED

When set, this indicates that the fault put the GPU into a state that requires a full adapter reset.

### -field DXGK_PAGE_FAULT_ENGINE_RESET_REQUIRED

When set, this indicates that the fault put the GPU into a state that requires a GPU engine reset.

### -field DXGK_PAGE_FAULT_FATAL_HARDWARE_ERROR

When set, this indicates that the system hardware, not just the GPU, cannot continue, and the OS should issue a bugcheck.

### -field DXGK_PAGE_FAULT_IOMMU

When set, this indicates that the faulting GPU's virtual address was mapped using IoMmu. When not set, the faulting GPU's virtual address was mapped using the GPU's memory management unit.

### -field DXGK_PAGE_FAULT_HW_CONTEXT_VALID

### -field DXGK_PAGE_FAULT_PROCESS_HANDLE_VALID

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>
