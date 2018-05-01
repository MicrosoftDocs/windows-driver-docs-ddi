---
UID: NF:wdm.MmGetSystemAddressForMdl
title: MmGetSystemAddressForMdl macro
author: windows-driver-content
description: The MmGetSystemAddressForMdl routine is obsolete for Windows 2000 and later versions of Windows, and for Windows Me.
old-location: kernel\mmgetsystemaddressformdl.htm
old-project: kernel
ms.assetid: e5366a28-a541-47bb-b158-af676ad46273
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: MmGetSystemAddressForMdl, MmGetSystemAddressForMdl routine [Kernel-Mode Driver Architecture], k106_fc92914d-81c3-4ae9-a12d-86003d55bb4d.xml, kernel.mmgetsystemaddressformdl, wdm/MmGetSystemAddressForMdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Obsolete for Windows 2000 and later versions of Windows, and for Windows Me. This routine is supported only for WDM drivers that must run on Windows 98. Otherwise, use MmGetSystemAddressForMdlSafe.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	MmGetSystemAddressForMdl
product: Windows
targetos: Windows
req.typenames: 
---

# MmGetSystemAddressForMdl macro


## -description


The <b>MmGetSystemAddressForMdl</b> routine is <u>obsolete</u> for Windows 2000 and later versions of Windows, and for Windows Me. It is supported only for WDM drivers that must run on Windows 98. Otherwise, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>.

<b>MmGetSystemAddressForMdl</b> is a macro that returns a nonpaged system-space virtual address for the buffer described by the MDL. It maps the physical pages described by a given MDL into system space, if they are not already mapped to system space. 


## -parameters




### -param MDL

TBD






#### - Mdl [in]

Pointer to a buffer whose corresponding base virtual address is to be mapped. 


## -remarks



Drivers of PIO devices call this routine to translate a virtual address range, described by the MDL at <b>Irp-&gt;MdlAddress</b>, for a user buffer to a system-space address range.

The MDL must describe nonpageable memory. In other words, the input MDL must describe an already locked-down user-space buffer returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a>, a locked-down buffer returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff554498">MmBuildMdlForNonPagedPool</a>, or system-space memory allocated from nonpaged pool, contiguous memory, or noncached memory.

The returned base address has the same offset as the virtual address in the MDL.

Windows 2000 issues a bug check if the attempt to map to system space fails. (Therefore, you should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a> instead). In Windows 98, this routine returns <b>NULL</b> in case of failure.  




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554498">MmBuildMdlForNonPagedPool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a>
 

 

