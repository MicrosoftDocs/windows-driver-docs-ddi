---
UID: NC:videoagp.PAGP_RESERVE_VIRTUAL
title: PAGP_RESERVE_VIRTUAL
author: windows-driver-content
description: The AgpReserveVirtual function reserves a range of virtual addresses for AGP.
old-location: display\agpreservevirtual.htm
old-project: display
ms.assetid: 966dfc6c-6830-4872-b411-2801e3a4b753
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AgpReserveVirtual, AgpReserveVirtual callback function [Display Devices], PAGP_RESERVE_VIRTUAL, VideoPort_Functions_ed4d4e19-25f2-4169-a80e-8c57c80ffd2b.xml, display.agpreservevirtual, videoagp/AgpReserveVirtual
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
-	AgpReserveVirtual
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---

# PAGP_RESERVE_VIRTUAL callback


## -description


The <b>AgpReserveVirtual</b> function reserves a range of virtual addresses for AGP.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param ProcessHandle [in]

Handle of the process in which to reserve the virtual address range. If <b>ProcessHandle</b> is 0, then the virtual address range is allocated in system space.


### -param PhysicalReserveContext [in]

Is the context handle that identifies the reserved physical address range with which to associate the virtual memory reservation. This context was obtained from <a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>.


### -param *VirtualReserveContext [out]

Is the location in which the video port driver writes a context handle that identifies the reserved virtual memory.


## -returns



<b>AgpReserveVirtual</b> returns the base address of the reserved virtual address range if successful; otherwise, returns <b>NULL</b>.




## -remarks



If <b>ProcessHandle</b> is not 0, then <b>AgpReserveVirtual</b> reserves, but does not commit, a range of virtual addresses in the address space of a user-mode process. In that case, you must call <a href="https://msdn.microsoft.com/8a3e7fcd-d838-47ad-a42b-7eb070f81418">AgpCommitVirtual</a> to map the reserved (user-mode) virtual addresses to physical addresses.

If <b>ProcessHandle</b> is 0, then <b>AgpReserveVirtual</b> allocates a range of virtual addresses in system space and automatically maps (commits) the entire range of virtual addresses to physical addresses. Even though <b>AgpReserveVirtual</b> commits the entire virtual range, you still must call <a href="https://msdn.microsoft.com/8a3e7fcd-d838-47ad-a42b-7eb070f81418">AgpCommitVirtual</a> before any code accesses the virtual range.

When you call <b>AgpReserveVirtual</b> to allocate a range of virtual addresses in system space (that is, if you set <b>ProcessHandle</b> to 0), the entire range of physical addresses identified by <b>PhysicalReserveContext</b> must be committed to locked pages of physical memory by a previous call to <a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a>.

The miniport driver can call <a href="https://msdn.microsoft.com/4e880b39-e0ee-4801-86b7-ffc06ed415ab">AgpReleaseVirtual</a> several times to reserve many smaller address ranges rather than one big range.

The miniport driver should call <a href="https://msdn.microsoft.com/4e880b39-e0ee-4801-86b7-ffc06ed415ab">AgpReleaseVirtual</a> to release the reserved virtual address range when it is no longer needed.




## -see-also




<a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a>



<a href="https://msdn.microsoft.com/8a3e7fcd-d838-47ad-a42b-7eb070f81418">AgpCommitVirtual</a>



<a href="https://msdn.microsoft.com/4e880b39-e0ee-4801-86b7-ffc06ed415ab">AgpReleaseVirtual</a>



<a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>
 

 

