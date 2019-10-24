---
UID: NC:videoagp.PAGP_COMMIT_PHYSICAL
title: PAGP_COMMIT_PHYSICAL (videoagp.h)
description: The AgpCommitPhysical function maps system (physical) memory to the specified range of AGP-decodable physical addresses.
old-location: display\agpcommitphysical.htm
tech.root: display
ms.assetid: 3c3a6936-7435-4a42-99e6-2c048613af23
ms.date: 05/10/2018
ms.keywords: AgpCommitPhysical, AgpCommitPhysical callback function [Display Devices], PAGP_COMMIT_PHYSICAL, PAGP_COMMIT_PHYSICAL callback, VideoPort_Functions_11f78058-194b-4407-b98b-1ae7cd0028f7.xml, display.agpcommitphysical, videoagp/AgpCommitPhysical
ms.topic: callback
f1_keywords:
 - "videoagp/AgpCommitPhysical"
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
- AgpCommitPhysical
product:
- Windows
targetos: Windows
req.typenames: 
---

# PAGP_COMMIT_PHYSICAL callback function


## -description


The <b>AgpCommitPhysical</b> function maps system (physical) memory to the specified range of AGP-decodable physical addresses.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the device extension of the miniport driver.


### -param PhysicalReserveContext [in]

Identifies a reserved physical address range. The context handle is obtained from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>.


### -param Pages [in]

Specifies the number of pages of system memory to commit.


### -param Offset [in]

Specifies the page offset at which to commit the pages. The offset is applied to the reserved physical address range associated with <b>PhysicalReserveContext</b>.


## -returns



<b>AgpCommitPhysical</b> returns <b>TRUE</b> if the mapping was successful, and <b>FALSE</b> otherwise.




## -remarks



A video miniport driver must first reserve physical addresses by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a> before it calls this function.

Do not call <b>AgpCommitPhysical</b> to commit addresses that have already been committed. If the range of pages that is specified by <b>PhysicalReserveContext</b>, <b>Pages</b>, and <b>Offset</b> includes any pages that were previously committed, <b>AgpCommitPhysical</b> might fail.

Video miniport drivers that run on Microsoft Windows 2000 should always reserve and commit a physical range whose size is a multiple of 64 kilobytes. Reserving or committing a physical range that is not a multiple of 64 kilobytes can result in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a> returning an invalid virtual address.

On Windows XP and later, <b>AgpCommitPhysical</b> automatically expands the committed range so that it is a multiple of 64 kilobytes.

When a video miniport driver calls <b>AgpCommitPhysical</b>, a portion of the physical address range identified by <b>PhysicalReserveContext</b> is mapped to locked pages of physical memory. The mapped portion begins <b>Offset</b> pages into the range identified by <b>PhysicalReserveContext</b>. The video miniport driver can access committed physical memory as if it were contiguous.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a>
 

 

