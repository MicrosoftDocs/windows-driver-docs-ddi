---
UID: NC:videoagp.PAGP_RESERVE_PHYSICAL
title: PAGP_RESERVE_PHYSICAL (videoagp.h)
description: The AgpReservePhysical function reserves a range of physical addresses on the system bus to which the AGP controller can respond.
old-location: display\agpreservephysical.htm
tech.root: display
ms.assetid: b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa
ms.date: 05/10/2018
ms.keywords: AgpReservePhysical, AgpReservePhysical callback function [Display Devices], PAGP_RESERVE_PHYSICAL, PAGP_RESERVE_PHYSICAL callback, VideoPort_Functions_9ce9c724-b077-4821-9b9a-adb3d16f5671.xml, display.agpreservephysical, videoagp/AgpReservePhysical
ms.topic: callback
f1_keywords:
 - "videoagp/AgpReservePhysical"
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
- AgpReservePhysical
product:
- Windows
targetos: Windows
req.typenames: 
---

# PAGP_RESERVE_PHYSICAL callback function


## -description


The <b>AgpReservePhysical</b> function reserves a range of physical addresses on the system bus to which the AGP controller can respond.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param Pages [in]

Specifies the number of pages that the video port driver should reserve.


### -param Caching [in]

Specifies the type of caching that the system should use. This parameter can be set to one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| **VpNonCached** | The system should not cache the range of addresses. | 
| **VpWriteCombined** | The system should use write-combined (WC) caching. For information about WC caching, see the [Write-Combining Memory in Video Miniport Drivers](https://docs.microsoft.com/previous-versions/windows/hardware/design/dn642116(v=vs.85))  website article. | 
| **VpCached** | The system should use ordinary caching. | 


### -param *PhysicalReserveContext [out]

Specifies the location in which the video port driver writes a context handle that identifies the reserved physical address space.


## -returns



<b>AgpReservePhysical</b> returns the base address of the reserved physical address range if successful; otherwise, it returns <b>NULL</b>.




## -remarks



Video miniport drivers that run on Microsoft Windows 2000 should always reserve a range whose size is a multiple of 64 kilobytes. Reserving a range that is not a multiple of 64 kilobytes can result in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a> returning an invalid virtual address.

On Microsoft Windows XP and later, <b>AgpReservePhysical</b> automatically expands the requested range to a multiple of 64 kilobytes.

Upon successful return, the AGP controller can respond to the reserved physical address range on the bus. However, the video miniport driver must first call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_physical">AgpCommitPhysical</a> to cause this memory to be committed before accessing it in order for the accessed results to be defined.

The miniport driver can call <b>AgpReservePhysical</b> several times to reserve many smaller address ranges rather than one big range.

The miniport driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_release_physical">AgpReleasePhysical</a> to release the physical address range when it is no longer needed. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_physical">AgpCommitPhysical</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_release_physical">AgpReleasePhysical</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a>
 

 

