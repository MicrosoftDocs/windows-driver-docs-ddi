---
UID: NF:ntddk.ZwTerminateProcess
title: ZwTerminateProcess function
author: windows-driver-content
description: The ZwTerminateProcess routine terminates a process and all of its threads.
old-location: kernel\zwterminateprocess.htm
old-project: kernel
ms.assetid: 3b5e6de3-f1f4-4d7f-8c97-56a20a453ca3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: NtTerminateProcess, ZwTerminateProcess, ZwTerminateProcess routine [Kernel-Mode Driver Architecture], k111_72c76674-5372-4662-9097-53d850d49afe.xml, kernel.zwterminateprocess, ntddk/NtTerminateProcess, ntddk/ZwTerminateProcess
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
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	ZwTerminateProcess
-	NtTerminateProcess
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# ZwTerminateProcess function


## -description


The <b>ZwTerminateProcess</b> routine terminates a process and all of its threads.


## -parameters




### -param ProcessHandle [in, optional]

A handle to the process object that represents the process to be terminated. 


### -param ExitStatus [in]

An NTSTATUS value that the operating system uses as the final status for the process and each of its threads. 


## -returns



<b>ZwTerminateProcess</b> returns STATUS_SUCCESS if the operation succeeds. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The specified handle is not a process handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The specified handle is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver cannot access the specified process object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
The specified process is already terminating. 

</td>
</tr>
</table>
 

If the caller specifies the current process in the <i>ProcessHandle</i> parameter, <b>ZwTerminateProcess</b> does not return.




## -remarks



To obtain a process handle that a driver can specify for the <i>ProcessHandle</i> parameter, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567022">ZwOpenProcess</a>. The handle must be a <a href="https://msdn.microsoft.com/4015d7bd-48f6-489b-a0e5-eca83758c5bb">kernel handle</a>.

Drivers must not specify the current process if resources have not been freed from the kernel stack, because the operating system will not unwind the kernel stack for the calling thread.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff557699">NtTerminateProcess</a>" instead of "<b>ZwTerminateProcess</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567022">ZwOpenProcess</a>
 

 

