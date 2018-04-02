---
UID: NF:ntddk.MmSecureVirtualMemory
title: MmSecureVirtualMemory function
author: windows-driver-content
description: The MmSecureVirtualMemory routine secures a user-space memory address range so that it cannot be freed and its protection type cannot be made more restrictive.
old-location: kernel\mmsecurevirtualmemory.htm
old-project: kernel
ms.assetid: e5c2d5d5-550e-42e5-b86a-f17e361925dc
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: MmSecureVirtualMemory, MmSecureVirtualMemory routine [Kernel-Mode Driver Architecture], k106_d85881bb-59a3-4494-afaa-55c49b71b64b.xml, kernel.mmsecurevirtualmemory, ntddk/MmSecureVirtualMemory
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
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmSecureVirtualMemory
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# MmSecureVirtualMemory function


## -description


The <b>MmSecureVirtualMemory</b> routine secures a user-space memory address range so that it cannot be freed and its protection type cannot be made more restrictive.


## -parameters




### -param Address [in]

The beginning of the user virtual address range to secure.


### -param Size [in]

The size, in bytes, of the virtual address range to secure.


### -param ProbeMode [in]

The most restrictive protection type that is allowed. Use PAGE_READWRITE to specify that address range must remain both readable and writable, or use PAGE_READONLY to specify the address range must only remain readable.


## -returns



On success, <b>MmSecureVirtualMemory</b> returns an opaque pointer value that the driver passes to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556395">MmUnsecureVirtualMemory</a> routine to unsecure the memory address range. If the routine is unable to secure the memory address range, it returns <b>NULL</b>.




## -remarks



<b>MmSecureVirtualMemory</b> can be used to avoid certain race conditions on user-mode buffers. For example, if a driver checks to see if the buffer is writable, but then the originating user-mode process changes the buffer to be read-only before the driver can write to the buffer, then a race condition can result. A driver that uses <b>MmSecureVirtualMemory</b> is guaranteed that if the requested protection mode is available, it cannot be changed until the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556395">MmUnsecureVirtualMemory</a>. The routine also protects against the originating user-mode process freeing the buffer. Here are a few guidelines about calling those routines:<ul>
<li>
If a driver calls <b>MmSecureVirtualMemory</b> and does not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556395">MmUnsecureVirtualMemory</a>, the memory is automatically unsecured when the process terminates.

</li>
<li>
If the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556395">MmUnsecureVirtualMemory</a>, it must call it in the context of the process in which the memory was originally secured, and before that process terminates.

</li>
<li>
Typically drivers need to reference the process when they secure the memory, then later call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549659">KeStackAttachProcess</a> to switch to the context of that process before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff556395">MmUnsecureVirtualMemory</a>.

</li>
<li>
To detect process termination drivers can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff559951">PsSetCreateProcessNotifyRoutine</a>. Alternatively, the process can submit an IRP with a cancel routine that is invoked by the I/O manager when the process is exiting. In the cancel routine the driver can attach to the process and call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556395">MmUnsecureVirtualMemory</a>.

</li>
</ul>


While calling <b>MmSecureVirtualMemory</b> on an address range prevents the address range from being freed or from having its protection changed, it does not protect against other types of raised exceptions. (For example, it does not protect against an exception raised when the system finds a bad disk block in the page file.)  Therefore, drivers must still wrap any memory accesses in a <b>try/except</b> block. Therefore, we recommend that drivers do not use this function. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556395">MmUnsecureVirtualMemory</a>
 

 

