---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY
title: "_DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY describes a residency allocation change operation.
old-location: display\dxgk_buildpagingbuffer_notifyresidency.htm
old-project: display
ms.assetid: 0E70F621-03CD-4593-88C7-DF6F2ADC902A
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY, DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY, d3dkmddi/DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY, display.dxgk_buildpagingbuffer_notifyresidency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY
product:
- Windows
targetos: Windows
req.typenames: DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY
---

# _DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY structure


## -description


<b> DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY</b> describes a residency allocation change operation.


## -struct-fields




### -field hAllocation

The kernel mode driver handle returned from <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>.


### -field PhysicalAddress

The physical address of the allocation. The physical address (0, 0) is invalid and is used when the allocation is being evicted.  


#### - Reserved

This member is not used and should be set to zero.


#### - Resident

Set to 0 when the allocation is evicted and set to 1 when the allocation is committed.


## -remarks



The paging operations is issued only for allocations, for which the kernel mode driver sets the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560966">DXGK_ALLOCATIONINFOFLAGS</a>::<b>ExplicitResidencyNotification</b> and <b>AccessedPhysically</b> flags.

The operation is issued after <i>FillVirtual</i> or <i>TransferVirtual</i> operations when the allocation is committed to a memory segment (<b>Resident</b> == 1). Note that the previous paging operations might not yet be finished by graphics processing unit (GPU).

The operation is issued before <i>TransferVirtual</i> operation when the allocation is evicted (<b>Resident</b> == 0) from a memory segment.


Note that the <i>NotifyResidency</i> operation will be issued only once during allocation eviction/commitment, while there might be several <i>TransferVirtual</i>/<i>FillVirtual</i> operations for a single allocation.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>
 

 

