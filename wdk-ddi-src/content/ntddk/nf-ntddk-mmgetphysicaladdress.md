---
UID: NF:ntddk.MmGetPhysicalAddress
title: MmGetPhysicalAddress function
author: windows-driver-content
description: The MmGetPhysicalAddress routine returns the physical address corresponding to a valid nonpaged virtual address.
old-location: kernel\mmgetphysicaladdress.htm
old-project: kernel
ms.assetid: 2381c1c2-d7fc-4cb2-bbdf-2a95c78c34d0
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: MmGetPhysicalAddress, MmGetPhysicalAddress routine [Kernel-Mode Driver Architecture], k106_1dc50500-ccd1-41a9-8a6c-55e3e283b00b.xml, kernel.mmgetphysicaladdress, ntddk/MmGetPhysicalAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmGetPhysicalAddress
product: Windows
targetos: Windows
req.typenames: 
---

# MmGetPhysicalAddress function


## -description


The <b>MmGetPhysicalAddress</b> routine returns the physical address corresponding to a valid nonpaged virtual address.


## -parameters




### -param BaseAddress [in]

Pointer to the virtual address for which to return the physical address. 


## -returns



<b>MmGetPhysicalAddress</b> returns the physical address that corresponds to the given virtual address.

Do not use this routine to obtain physical addresses for use with DMA operations. For information about the proper techniques for performing DMA operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540519">Adapter Objects and DMA</a>.




## -remarks



Callers of <b>MmGetPhysicalAddress</b> can be running at any IRQL, provided that the <i>BaseAddress</i> value is valid.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554572">MmIsAddressValid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554588">MmIsNonPagedSystemAddressValid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554618">MmMapIoSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a>
 

 

