---
UID: NF:ntddk.ZwTerminateProcess
title: ZwTerminateProcess function (ntddk.h)
description: The ZwTerminateProcess routine terminates a process and all of its threads.
old-location: kernel\zwterminateprocess.htm
tech.root: kernel
ms.assetid: 3b5e6de3-f1f4-4d7f-8c97-56a20a453ca3
ms.date: 04/30/2018
ms.keywords: NtTerminateProcess, ZwTerminateProcess, ZwTerminateProcess routine [Kernel-Mode Driver Architecture], k111_72c76674-5372-4662-9097-53d850d49afe.xml, kernel.zwterminateprocess, ntddk/NtTerminateProcess, ntddk/ZwTerminateProcess
ms.topic: function
f1_keywords:
 - "ntddk/ZwTerminateProcess"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwTerminateProcess
- NtTerminateProcess
product:
- Windows
targetos: Windows
req.typenames: 
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



To obtain a process handle that a driver can specify for the <i>ProcessHandle</i> parameter, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ntopenprocess">ZwOpenProcess</a>. The handle must be a *kernel handle*, a handle that can only be accessed in kernel mode. A handle is a kernel handle if it is created with the OBJ_KERNEL_HANDLE flag. For more info see [InitializeObjectAttributes](https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfwdm/nf-wudfwdm-initializeobjectattributes).

Drivers must not specify the current process if resources have not been freed from the kernel stack, because the operating system will not unwind the kernel stack for the calling thread.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwterminateprocess">NtTerminateProcess</a>" instead of "<b>ZwTerminateProcess</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ntopenprocess">ZwOpenProcess</a>
 

 

