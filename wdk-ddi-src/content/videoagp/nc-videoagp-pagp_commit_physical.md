---
UID: NC:videoagp.PAGP_COMMIT_PHYSICAL
title: PAGP_COMMIT_PHYSICAL
author: windows-driver-content
description: The AgpCommitPhysical function maps system (physical) memory to the specified range of AGP-decodable physical addresses.
old-location: display\agpcommitphysical.htm
old-project: display
ms.assetid: 3c3a6936-7435-4a42-99e6-2c048613af23
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AgpCommitPhysical, AgpCommitPhysical callback function [Display Devices], PAGP_COMMIT_PHYSICAL, VideoPort_Functions_11f78058-194b-4407-b98b-1ae7cd0028f7.xml, display.agpcommitphysical, videoagp/AgpCommitPhysical
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
-	AgpCommitPhysical
product:
- Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---

# PAGP_COMMIT_PHYSICAL callback


## -description


The <b>AgpCommitPhysical</b> function maps system (physical) memory to the specified range of AGP-decodable physical addresses.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the device extension of the miniport driver.


### -param PhysicalReserveContext [in]

Identifies a reserved physical address range. The context handle is obtained from <a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>.


### -param Pages [in]

Specifies the number of pages of system memory to commit.


### -param Offset [in]

Specifies the page offset at which to commit the pages. The offset is applied to the reserved physical address range associated with <b>PhysicalReserveContext</b>.


## -returns



<b>AgpCommitPhysical</b> returns <b>TRUE</b> if the mapping was successful, and <b>FALSE</b> otherwise.




## -remarks



A video miniport driver must first reserve physical addresses by calling <a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a> before it calls this function.

Do not call <b>AgpCommitPhysical</b> to commit addresses that have already been committed. If the range of pages that is specified by <b>PhysicalReserveContext</b>, <b>Pages</b>, and <b>Offset</b> includes any pages that were previously committed, <b>AgpCommitPhysical</b> might fail.

Video miniport drivers that run on Microsoft Windows 2000 should always reserve and commit a physical range whose size is a multiple of 64 kilobytes. Reserving or committing a physical range that is not a multiple of 64 kilobytes can result in <a href="https://msdn.microsoft.com/966dfc6c-6830-4872-b411-2801e3a4b753">AgpReserveVirtual</a> or <a href="https://msdn.microsoft.com/8a3e7fcd-d838-47ad-a42b-7eb070f81418">AgpCommitVirtual</a> returning an invalid virtual address.

On Windows XP and later, <b>AgpCommitPhysical</b> automatically expands the committed range so that it is a multiple of 64 kilobytes.

When a video miniport driver calls <b>AgpCommitPhysical</b>, a portion of the physical address range identified by <b>PhysicalReserveContext</b> is mapped to locked pages of physical memory. The mapped portion begins <b>Offset</b> pages into the range identified by <b>PhysicalReserveContext</b>. The video miniport driver can access committed physical memory as if it were contiguous.




## -see-also




<a href="https://msdn.microsoft.com/8a3e7fcd-d838-47ad-a42b-7eb070f81418">AgpCommitVirtual</a>



<a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>



<a href="https://msdn.microsoft.com/966dfc6c-6830-4872-b411-2801e3a4b753">AgpReserveVirtual</a>
 

 

