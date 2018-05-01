---
UID: NC:videoagp.PAGP_RESERVE_PHYSICAL
title: PAGP_RESERVE_PHYSICAL
author: windows-driver-content
description: The AgpReservePhysical function reserves a range of physical addresses on the system bus to which the AGP controller can respond.
old-location: display\agpreservephysical.htm
old-project: display
ms.assetid: b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: AgpReservePhysical, AgpReservePhysical callback function [Display Devices], PAGP_RESERVE_PHYSICAL, PAGP_RESERVE_PHYSICAL callback, VideoPort_Functions_9ce9c724-b077-4821-9b9a-adb3d16f5671.xml, display.agpreservephysical, videoagp/AgpReservePhysical
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	videoagp.h
api_name:
-	AgpReservePhysical
product: Windows
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

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>VpNonCached</b>

</td>
<td>
The system should not cache the range of addresses.

</td>
</tr>
<tr>
<td>
<b>VpWriteCombined</b>

</td>
<td>
The system should use write-combined (WC) caching. For information about WC caching, see the <a href="https://msdn.microsoft.com/library/windows/hardware/dn642116">Write-Combining Memory in Video Miniport Drivers</a> website article.

</td>
</tr>
<tr>
<td>
<b>VpCached</b>

</td>
<td>
The system should use ordinary caching.

</td>
</tr>
</table>
 


### -param *PhysicalReserveContext [out]

Specifies the location in which the video port driver writes a context handle that identifies the reserved physical address space.


## -returns



<b>AgpReservePhysical</b> returns the base address of the reserved physical address range if successful; otherwise, it returns <b>NULL</b>.




## -remarks



Video miniport drivers that run on Microsoft Windows 2000 should always reserve a range whose size is a multiple of 64 kilobytes. Reserving a range that is not a multiple of 64 kilobytes can result in <a href="https://msdn.microsoft.com/966dfc6c-6830-4872-b411-2801e3a4b753">AgpReserveVirtual</a> or <a href="https://msdn.microsoft.com/8a3e7fcd-d838-47ad-a42b-7eb070f81418">AgpCommitVirtual</a> returning an invalid virtual address.

On Microsoft Windows XP and later, <b>AgpReservePhysical</b> automatically expands the requested range to a multiple of 64 kilobytes.

Upon successful return, the AGP controller can respond to the reserved physical address range on the bus. However, the video miniport driver must first call <a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a> to cause this memory to be committed before accessing it in order for the accessed results to be defined.

The miniport driver can call <b>AgpReservePhysical</b> several times to reserve many smaller address ranges rather than one big range.

The miniport driver should call <a href="https://msdn.microsoft.com/4da0f5cb-a017-4df5-958b-c76b7a08495a">AgpReleasePhysical</a> to release the physical address range when it is no longer needed. 




## -see-also




<a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a>



<a href="https://msdn.microsoft.com/4da0f5cb-a017-4df5-958b-c76b7a08495a">AgpReleasePhysical</a>



<a href="https://msdn.microsoft.com/966dfc6c-6830-4872-b411-2801e3a4b753">AgpReserveVirtual</a>
 

 

