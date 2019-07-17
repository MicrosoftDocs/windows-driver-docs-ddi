---
UID: NC:videoagp.PAGP_COMMIT_VIRTUAL
title: PAGP_COMMIT_VIRTUAL (videoagp.h)
description: The AgpCommitVirtual function maps reserved virtual memory to an associated range of AGP-decodable physical addresses.
old-location: display\agpcommitvirtual.htm
tech.root: display
ms.assetid: 8a3e7fcd-d838-47ad-a42b-7eb070f81418
ms.date: 05/10/2018
ms.keywords: AgpCommitVirtual, AgpCommitVirtual callback function [Display Devices], PAGP_COMMIT_VIRTUAL, PAGP_COMMIT_VIRTUAL callback, VideoPort_Functions_74f16518-6071-45bb-a44d-80fe042814ea.xml, display.agpcommitvirtual, videoagp/AgpCommitVirtual
ms.topic: callback
f1_keywords:
 - "videoagp/AgpCommitVirtual"
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- videoagp.h
api_name:
- AgpCommitVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# PAGP_COMMIT_VIRTUAL callback function


## -description


The <b>AgpCommitVirtual</b> function maps reserved virtual memory to an associated range of AGP-decodable physical addresses.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the device extension of the miniport driver'.


### -param VirtualReserveContext [in]

Identifies a reserved virtual address range. The context handle was obtained from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a>.


### -param Pages [in]

Specifies the number of pages of virtual memory to map.


### -param Offset [in]

Specifies the page offset at which to commit the pages. The offset is applied to the reserved virtual address range that is identified by <b>VirtualReserveContext</b>.


## -returns



<b>AgpCommitVirtual</b> returns the virtual address for the base of the committed pages if the mapping succeeded; otherwise returns <b>NULL</b>.




## -remarks



Before calling <b>AgpCommitVirtual</b> to commit a range of virtual pages, you must do the following:

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a> to reserve a range of physical addresses for the GPU to use.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_commit_physical">AgpCommitPhysical</a> to map a portion (or all) of the reserved physical addresses to locked pages in system memory.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a> to reserve a range of virtual addresses that is associated with the range of physical addresses reserved by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>.

</li>
</ul>
After these items are completed, you can call <b>AgpCommitVirtual</b> to map a portion of the reserved virtual pages to pages that have already been mapped and locked by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_commit_physical">AgpCommitPhysical</a>. You must not attempt to map a page of virtual addresses if the corresponding page of physical addresses has not already been mapped.

Video miniport drivers that run on Microsoft Windows 2000 should always commit a virtual range whose size is a multiple of 64 kilobytes. If you call <b>AgpCommitVirtual</b> to commit a virtual range that is not a multiple of 64 kilobytes, it can return an invalid virtual address.

On Windows XP and later, <b>AgpCommitVirtual</b> automatically expands the committed range so that it is a multiple of 64 kilobytes.

When a miniport driver calls <b>AgpCommitVirtual</b>, a portion of the virtual address range identified by <b>VirtualReserveContext</b> is mapped to physical addresses. The mapped portion begins <i>Offset</i> pages into the virtual address range that is identified by <b>VirtualReserveContext</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_free_virtual">AgpFreeVirtual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a>
 

 

