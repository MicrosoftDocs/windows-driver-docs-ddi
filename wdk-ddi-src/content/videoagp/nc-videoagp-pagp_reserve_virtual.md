---
UID: NC:videoagp.PAGP_RESERVE_VIRTUAL
title: PAGP_RESERVE_VIRTUAL
author: windows-driver-content
description: The AgpReserveVirtual function reserves a range of virtual addresses for AGP.
old-location: display\agpreservevirtual.htm
old-project: display
ms.assetid: 966dfc6c-6830-4872-b411-2801e3a4b753
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.agpreservevirtual, AgpReserveVirtual callback function [Display Devices], AgpReserveVirtual, PAGP_RESERVE_VIRTUAL, PAGP_RESERVE_VIRTUAL, videoagp/AgpReserveVirtual, VideoPort_Functions_ed4d4e19-25f2-4169-a80e-8c57c80ffd2b.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	videoagp.h
apiname:
-	AgpReserveVirtual
product: Windows
targetos: Windows
req.typenames: "*PVP_SCATTER_GATHER_LIST, VP_SCATTER_GATHER_LIST"
---

# PAGP_RESERVE_VIRTUAL callback


## -description


The <b>AgpReserveVirtual</b> function reserves a range of virtual addresses for AGP.


## -prototype


````
PAGP_RESERVE_VIRTUAL AgpReserveVirtual;

PVOID APIENTRY AgpReserveVirtual(
  _In_  PVOID  HwDeviceExtension,
  _In_  HANDLE ProcessHandle,
  _In_  PVOID  PhysicalReserveContext,
  _Out_ PVOID  *VirtualReserveContext
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param ProcessHandle [in]

Handle of the process in which to reserve the virtual address range. If <b>ProcessHandle</b> is 0, then the virtual address range is allocated in system space.


### -param PhysicalReserveContext [in]

Is the context handle that identifies the reserved physical address range with which to associate the virtual memory reservation. This context was obtained from <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>.


### -param *VirtualReserveContext






#### - VirtualReserveContext [out]

Is the location in which the video port driver writes a context handle that identifies the reserved virtual memory.


## -returns


<b>AgpReserveVirtual</b> returns the base address of the reserved virtual address range if successful; otherwise, returns <b>NULL</b>.



## -remarks


If <b>ProcessHandle</b> is not 0, then <b>AgpReserveVirtual</b> reserves, but does not commit, a range of virtual addresses in the address space of a user-mode process. In that case, you must call <a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a> to map the reserved (user-mode) virtual addresses to physical addresses.

If <b>ProcessHandle</b> is 0, then <b>AgpReserveVirtual</b> allocates a range of virtual addresses in system space and automatically maps (commits) the entire range of virtual addresses to physical addresses. Even though <b>AgpReserveVirtual</b> commits the entire virtual range, you still must call <a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a> before any code accesses the virtual range.

When you call <b>AgpReserveVirtual</b> to allocate a range of virtual addresses in system space (that is, if you set <b>ProcessHandle</b> to 0), the entire range of physical addresses identified by <b>PhysicalReserveContext</b> must be committed to locked pages of physical memory by a previous call to <a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>.

The miniport driver can call <a href="..\videoagp\nc-videoagp-pagp_release_virtual.md">AgpReleaseVirtual</a> several times to reserve many smaller address ranges rather than one big range.

The miniport driver should call <a href="..\videoagp\nc-videoagp-pagp_release_virtual.md">AgpReleaseVirtual</a> to release the reserved virtual address range when it is no longer needed.



## -see-also

<a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a>

<a href="..\videoagp\nc-videoagp-pagp_release_virtual.md">AgpReleaseVirtual</a>

<a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>

<a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PAGP_RESERVE_VIRTUAL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

