---
UID: NE:d3dkmddi._DXGK_BUILDPAGINGBUFFER_OPERATION
title: "_DXGK_BUILDPAGINGBUFFER_OPERATION"
author: windows-driver-content
description: Indicates the type of memory operation to perform.
old-location: display\dxgk_buildpagingbuffer_operation.htm
ms.assetid: D170D828-A0BC-4CBC-9F3F-E384AAD11FCC
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_OPERATION, DXGK_BUILDPAGINGBUFFER_OPERATION enumeration [Display Devices], DXGK_OPERATION_COPY_PAGE_TABLE_ENTRIES, DXGK_OPERATION_DISCARD_CONTENT, DXGK_OPERATION_FILL, DXGK_OPERATION_FLUSH_TLB, DXGK_OPERATION_INIT_CONTEXT_RESOURCE, DXGK_OPERATION_MAP_APERTURE_SEGMENT, DXGK_OPERATION_NOTIFY_RESIDENCY, DXGK_OPERATION_READ_PHYSICAL, DXGK_OPERATION_SPECIAL_LOCK_TRANSFER, DXGK_OPERATION_TRANSFER, DXGK_OPERATION_UNMAP_APERTURE_SEGMENT, DXGK_OPERATION_UPDATE_CONTEXT_ALLOCATION, DXGK_OPERATION_UPDATE_PAGE_TABLE, DXGK_OPERATION_VIRTUAL_FILL, DXGK_OPERATION_VIRTUAL_TRANSFER, DXGK_OPERATION_WRITE_PHYSICAL, _DXGK_BUILDPAGINGBUFFER_OPERATION, d3dkmddi/, d3dkmddi/DXGK_BUILDPAGINGBUFFER_OPERATION, d3dkmddi/DXGK_OPERATION_COPY_PAGE_TABLE_ENTRIES, d3dkmddi/DXGK_OPERATION_DISCARD_CONTENT, d3dkmddi/DXGK_OPERATION_FILL, d3dkmddi/DXGK_OPERATION_FLUSH_TLB, d3dkmddi/DXGK_OPERATION_INIT_CONTEXT_RESOURCE, d3dkmddi/DXGK_OPERATION_MAP_APERTURE_SEGMENT, d3dkmddi/DXGK_OPERATION_NOTIFY_RESIDENCY, d3dkmddi/DXGK_OPERATION_READ_PHYSICAL, d3dkmddi/DXGK_OPERATION_SPECIAL_LOCK_TRANSFER, d3dkmddi/DXGK_OPERATION_TRANSFER, d3dkmddi/DXGK_OPERATION_UNMAP_APERTURE_SEGMENT, d3dkmddi/DXGK_OPERATION_UPDATE_CONTEXT_ALLOCATION, d3dkmddi/DXGK_OPERATION_UPDATE_PAGE_TABLE, d3dkmddi/DXGK_OPERATION_VIRTUAL_FILL, d3dkmddi/DXGK_OPERATION_VIRTUAL_TRANSFER, d3dkmddi/DXGK_OPERATION_WRITE_PHYSICAL, display.dxgk_buildpagingbuffer_operation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_BUILDPAGINGBUFFER_OPERATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_BUILDPAGINGBUFFER_OPERATION
---

# _DXGK_BUILDPAGINGBUFFER_OPERATION enumeration


## -description


Indicates the type of memory operation to perform.


## -enum-fields




### -field DXGK_OPERATION_TRANSFER

Perform a transfer operation that moves the content of an allocation from one location to another.


### -field DXGK_OPERATION_FILL

Fill an allocation with a specified pattern.


### -field DXGK_OPERATION_DISCARD_CONTENT

Notifies the driver that an allocation is discarded from the allocation's current location in a memory segment (that is, the allocation is evicted and not copied back to system memory).


### -field DXGK_OPERATION_READ_PHYSICAL

Perform a read-physical operation that reads from a specified physical memory address.


### -field DXGK_OPERATION_WRITE_PHYSICAL

Perform a write-physical operation that writes to a specified physical memory address.


### -field DXGK_OPERATION_MAP_APERTURE_SEGMENT

Perform a map-aperture-segment operation that maps a memory descriptor list (MDL) into a range of an aperture segment.


### -field DXGK_OPERATION_UNMAP_APERTURE_SEGMENT

Perform an unmap-aperture-segment operation that unmaps a previously mapped range of an aperture segment.


### -field DXGK_OPERATION_SPECIAL_LOCK_TRANSFER

Perform a special transfer operation that moves the content of an allocation from one location to another. In this operation, the content of the allocation is transferred from or to the alternate virtual address that was set up for the allocation (that is, when the <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> function was called with the <b>UseAlternateVA</b> bit-field flag set).


### -field DXGK_OPERATION_VIRTUAL_TRANSFER

The operation is used to transfer allocation content between locations in memory. 


### -field DXGK_OPERATION_VIRTUAL_FILL

The operation is used to fill an allocation with a pattern.


### -field DXGK_OPERATION_INIT_CONTEXT_RESOURCE

Perform an context initialization operation for a GPU context or device-specific context. This value is supported beginning with Windows 8.


<div class="alert"><b>Note</b>  The display miniport driver allocates context resources by calling <a href="https://msdn.microsoft.com/b6b142a4-20eb-4368-bd7f-8a25f4fe48ca">DxgkCbCreateContextAllocation</a>.</div>
<div> </div>

### -field DXGK_OPERATION_UPDATE_PAGE_TABLE

The operation is called to allow the kernel mode driver to build a command buffer to update a page table. 


### -field DXGK_OPERATION_FLUSH_TLB

This operation instructs GPU to flush <i>translation look-aside buffer</i> entries, which belong to the given root page table. 


### -field DXGK_OPERATION_UPDATE_CONTEXT_ALLOCATION

This operation is used to update the content of a context or device allocation. 


### -field DXGK_OPERATION_COPY_PAGE_TABLE_ENTRIES

This operation is called to copy page table entries from one location to another.


### -field DXGK_OPERATION_NOTIFY_RESIDENCY

The paging operation is issued every time an allocation residency is changed (when allocation is evicted or committed).


### -field DXGK_OPERATION_SIGNAL_MONITORED_FENCE





