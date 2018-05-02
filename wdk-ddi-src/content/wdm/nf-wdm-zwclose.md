---
UID: NF:wdm.ZwClose
title: ZwClose function
author: windows-driver-content
description: The ZwClose routine closes an object handle.
old-location: kernel\zwclose.htm
old-project: kernel
ms.assetid: 35f335db-416b-4a17-b84c-d440b34ed199
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: NtClose, ZwClose, ZwClose routine [Kernel-Mode Driver Architecture], k111_6311836b-aa48-46f1-a64b-d94d5bb95f16.xml, kernel.zwclose, wdm/NtClose, wdm/ZwClose
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwClose
-	NtClose
product: Windows
targetos: Windows
req.typenames: 
---

# ZwClose function


## -description


The <b>ZwClose</b> routine closes an object handle. 


## -parameters




### -param Handle [in]

Handle to an object of any type. 


## -returns



<b>ZwClose</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. In particular, it returns STATUS_INVALID_HANDLE if <i>Handle</i> is not a valid handle, or STATUS_HANDLE_NOT_CLOSABLE if the calling thread does not have permission to close the handle.




## -remarks



<b>ZwClose</b> is a generic routine that operates on any type of object.

Closing an open object handle causes that handle to become invalid. The system also decrements the handle count for the object and checks whether the object can be deleted. The system does not actually delete the object until all of the object's handles are closed and no referenced pointers remain.

A driver must close every handle that it opens as soon as the handle is no longer required. Kernel handles, which are those that are opened by a system thread or by specifying the OBJ_KERNEL_HANDLE flag, can be closed only when the previous processor mode is <b>KernelMode</b>. This requirement applies both to system threads and to dispatch routines for IRPs that were issued from kernel mode. (For more information about the previous processor mode, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545288">ExGetPreviousMode</a>.) For example, a handle that <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> returns to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine cannot subsequently be closed by the same driver's <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">dispatch routines</a>. A <b>DriverEntry</b> routine runs in a system process, whereas dispatch routines usually run either in the context of the thread issuing the current I/O request, or, for lower-level drivers, in an arbitrary thread context.

A nonkernel handle can be closed only if one of two conditions is met: The previous processor mode is <b>KernelMode</b>, or the calling thread has sufficient permission to close the handle. An example of the latter occurs when the calling thread is the one that created the handle.

Callers of <b>ZwClose</b> should not assume that this routine automatically waits for all I/O to complete prior to returning. 

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtClose</b>" instead of "<b>ZwClose</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566421">ZwCreateDirectoryObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567029">ZwOpenSection</a>
 

 

