---
UID: NE:d3dkmdt._DXGK_PAGE_FAULT_FLAGS
title: "_DXGK_PAGE_FAULT_FLAGS"
author: windows-driver-content
description: DXGK_PAGE_FAULT_FLAGS enumeration describes the nature of the page fault that has occurred and the prescribed OS recovery action.
old-location: display\dxgk_page_fault_flags.htm
old-project: display
ms.assetid: 3AF0646D-5405-4A35-8352-7E32BCA5DD24
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_PAGE_FAULT_ADAPTER_RESET_REQUIRED, DXGK_PAGE_FAULT_ENGINE_RESET_REQUIRED, DXGK_PAGE_FAULT_FATAL_HARDWARE_ERROR, DXGK_PAGE_FAULT_FENCE_INVALID, DXGK_PAGE_FAULT_FLAGS, DXGK_PAGE_FAULT_FLAGS enumeration [Display Devices], DXGK_PAGE_FAULT_IOMMU, DXGK_PAGE_FAULT_WRITE, _DXGK_PAGE_FAULT_FLAGS, d3dkmdt/DXGK_PAGE_FAULT_ADAPTER_RESET_REQUIRED, d3dkmdt/DXGK_PAGE_FAULT_ENGINE_RESET_REQUIRED, d3dkmdt/DXGK_PAGE_FAULT_FATAL_HARDWARE_ERROR, d3dkmdt/DXGK_PAGE_FAULT_FENCE_INVALID, d3dkmdt/DXGK_PAGE_FAULT_FLAGS, d3dkmdt/DXGK_PAGE_FAULT_IOMMU, d3dkmdt/DXGK_PAGE_FAULT_WRITE, display.dxgk_page_fault_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmdt.h
api_name:
-	DXGK_PAGE_FAULT_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_PAGE_FAULT_FLAGS
---

# _DXGK_PAGE_FAULT_FLAGS enumeration


## -description


<b>DXGK_PAGE_FAULT_FLAGS</b> enumeration describes the nature of the page fault that has occurred and the prescribed OS recovery action.


## -syntax


````
typedef enum _DXGK_PAGE_FAULT_FLAGS { 
  DXGK_PAGE_FAULT_WRITE                   = 0x1,
  DXGK_PAGE_FAULT_FENCE_INVALID           = 0x2,
  DXGK_PAGE_FAULT_ADAPTER_RESET_REQUIRED  = 0x4,
  DXGK_PAGE_FAULT_ENGINE_RESET_REQUIRED   = 0x8,
  DXGK_PAGE_FAULT_FATAL_HARDWARE_ERROR    = 0x10,
  DXGK_PAGE_FAULT_IOMMU                   = 0x20
} DXGK_PAGE_FAULT_FLAGS;
````


## -enum-fields




### -field DXGK_PAGE_FAULT_WRITE

When set, this indicates that the faulted GPU virtual operation was a write operation.


### -field DXGK_PAGE_FAULT_FENCE_INVALID

When set, this indicates that a faulting packet could not be determined. In this case, the OS will have to perform a GPU reset action to clear the GPU error state, and one of the subsequent bits will have to be set.

When not set, this indicates that the DMA packet submitted with <b>FaultedFenceId</b> (in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure) was the cause of the fault. Similar to how the preemption and completion fences are handled, the OS will treat all pending packets with fence IDs less than <b>FaultedFenceId</b> as completed, and the driver will be required to advance its notion of the completed fence ID to <b>FaultedFenceId</b>.




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

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_PAGE_FAULT_FLAGS enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

