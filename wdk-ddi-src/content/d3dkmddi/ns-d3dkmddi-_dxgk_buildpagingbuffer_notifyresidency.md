---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY
title: "_DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY describes a residency allocation change operation.
old-location: display\dxgk_buildpagingbuffer_notifyresidency.htm
old-project: display
ms.assetid: 0E70F621-03CD-4593-88C7-DF6F2ADC902A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY structure [Display Devices], d3dkmddi/DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY, display.dxgk_buildpagingbuffer_notifyresidency, DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY, _DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY
product: Windows
targetos: Windows
req.typenames: DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY
---

# _DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY structure


## -description


<b> DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY</b> describes a residency allocation change operation.


## -syntax


````
typedef struct _DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY {
  HANDLE                  hAllocation;
  D3DGPU_PHYSICAL_ADDRESS PhysicalAddress;
  union {
    UINT Resident  :1;
    UINT Reserved  :31;
  };
} DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY;
````


## -struct-fields




### -field hAllocation

The kernel mode driver handle returned from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>.


### -field PhysicalAddress

The physical address of the allocation. The physical address (0, 0) is invalid and is used when the allocation is being evicted.  


### -field Resident

Set to 0 when the allocation is evicted and set to 1 when the allocation is committed.


### -field Reserved

This member is not used and should be set to zero.


## -remarks



The paging operations is issued only for allocations, for which the kernel mode driver sets the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfoflags.md">DXGK_ALLOCATIONINFOFLAGS</a>::<b>ExplicitResidencyNotification</b> and <b>AccessedPhysically</b> flags.

The operation is issued after <i>FillVirtual</i> or <i>TransferVirtual</i> operations when the allocation is committed to a memory segment (<b>Resident</b> == 1). Note that the previous paging operations might not yet be finished by graphics processing unit (GPU).

The operation is issued before <i>TransferVirtual</i> operation when the allocation is evicted (<b>Resident</b> == 0) from a memory segment.


Note that the <i>NotifyResidency</i> operation will be issued only once during allocation eviction/commitment, while there might be several <i>TransferVirtual</i>/<i>FillVirtual</i> operations for a single allocation.





## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

