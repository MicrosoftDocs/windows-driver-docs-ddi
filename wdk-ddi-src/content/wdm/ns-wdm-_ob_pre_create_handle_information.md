---
UID: NS:wdm._OB_PRE_CREATE_HANDLE_INFORMATION
title: "_OB_PRE_CREATE_HANDLE_INFORMATION"
author: windows-driver-content
description: The OB_PRE_CREATE_HANDLE_INFORMATION structure provides information to an ObjectPreCallback routine about a thread or process handle that is being opened.
old-location: kernel\ob_pre_create_handle_information.htm
old-project: kernel
ms.assetid: 50fd7666-cdec-4bdb-b350-2c2222124020
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*POB_PRE_CREATE_HANDLE_INFORMATION, OB_PRE_CREATE_HANDLE_INFORMATION, OB_PRE_CREATE_HANDLE_INFORMATION structure [Kernel-Mode Driver Architecture], POB_PRE_CREATE_HANDLE_INFORMATION, POB_PRE_CREATE_HANDLE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _OB_PRE_CREATE_HANDLE_INFORMATION, kernel.ob_pre_create_handle_information, kstruct_c_e7efa519-bfcd-4f16-9723-294f061bea51.xml, wdm/OB_PRE_CREATE_HANDLE_INFORMATION, wdm/POB_PRE_CREATE_HANDLE_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of the Windows operating system.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	OB_PRE_CREATE_HANDLE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: OB_PRE_CREATE_HANDLE_INFORMATION, *POB_PRE_CREATE_HANDLE_INFORMATION
---

# _OB_PRE_CREATE_HANDLE_INFORMATION structure


## -description


The <b>OB_PRE_CREATE_HANDLE_INFORMATION</b> structure provides information to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a> routine about a thread or process handle that is being opened.


## -struct-fields




### -field DesiredAccess

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that specifies the access rights to grant for the handle. By default, this member equals <i>OriginalDesiredAccess</i>, but the <i>ObjectPreCallback</i> routine can modify this value to restrict the access that is granted.

Drivers can use the following flags for handles to processes:

<table>
<tr>
<th>Flag</th>
<th>Allowed operations</th>
</tr>
<tr>
<td>
PROCESS_CREATE_PROCESS

</td>
<td>
Create a new child process of the process.

</td>
</tr>
<tr>
<td>
PROCESS_CREATE_THREAD

</td>
<td>
Create a new thread in the context of the process.

</td>
</tr>
<tr>
<td>
PROCESS_DUP_HANDLE

</td>
<td>
Duplicate handles to or from the context of the process, such as by calling the user-mode <b>DuplicateHandle</b> routine.

</td>
</tr>
<tr>
<td>
PROCESS_SET_QUOTA

</td>
<td>
Set the working set size for the process, such as by calling the user-mode <b>SetProcessWorkingSetSize</b> routine.

</td>
</tr>
<tr>
<td>
PROCESS_SET_INFORMATION

</td>
<td>
Modify process settings, such as by calling the user-mode <b>SetPriorityClass</b> routine.

</td>
</tr>
<tr>
<td>
PROCESS_SUSPEND_RESUME

</td>
<td>
Suspend or resume the process.

</td>
</tr>
<tr>
<td>
PROCESS_TERMINATE

</td>
<td>
Terminate the process, such as by calling the user-mode <b>TerminateProcess</b> routine..

</td>
</tr>
<tr>
<td>
PROCESS_VM_OPERATION

</td>
<td>
Modify the address space of the process, such as by calling the user-mode <b>WriteProcessMemory</b> and <b>VirtualProtectEx</b> routines.

</td>
</tr>
<tr>
<td>
PROCESS_VM_WRITE

</td>
<td>
Write to the address space of the process, such as by calling the user-mode <b>WriteProcessMemory</b> routine.

</td>
</tr>
</table>
 

Drivers can use the following flags for handles to threads:

<table>
<tr>
<th>Flag</th>
<th>Allowed operations</th>
</tr>
<tr>
<td>
THREAD_DIRECT_IMPERSONATION

</td>
<td>
Enable a server thread to impersonate one of its clients.

</td>
</tr>
<tr>
<td>
THREAD_IMPERSONATE

</td>
<td>
Impersonate the operating system's anonymous logon token, such as by calling the user-mode <b>ImpersonateAnonymousToken</b> routine.

</td>
</tr>
<tr>
<td>
THREAD_SET_CONTEXT

</td>
<td>
Modify the thread's execution context, such as by calling the user-mode <b>SetThreadContext</b> routine.

</td>
</tr>
<tr>
<td>
THREAD_SET_INFORMATION

</td>
<td>
Modify thread settings, such as by calling the user-mode <b>SetThreadIdealProcessor</b> routine. The operations that are permitted by this access right are a superset of those that are permitted by the THREAD_SET_LIMITED_INFORMATION access right.

</td>
</tr>
<tr>
<td>
THREAD_SET_LIMITED_INFORMATION

</td>
<td>
Modify a limited set of thread settings, such as by calling the user-mode <b>SetThreadAffinityMask</b> and <b>SetThreadPriorityBoost</b> routines.

</td>
</tr>
<tr>
<td>
THREAD_SET_THREAD_TOKEN

</td>
<td>
Modify properties of the thread's impersonation token, such as by calling the user-mode <b>SetTokenInformation</b> routine.

</td>
</tr>
<tr>
<td>
THREAD_SUSPEND_RESUME

</td>
<td>
Suspend or resume the thread, such as by calling the user-mode <b>SuspendThread</b> and <b>ResumeThread</b> routines.

</td>
</tr>
<tr>
<td>
THREAD_TERMINATE

</td>
<td>
Terminate the thread, such as by calling the user-mode <b>TerminateThread</b> routine.

</td>
</tr>
</table>
 


### -field OriginalDesiredAccess

An ACCESS_MASK value that specifies the original access that was requested for the handle.


## -remarks



You can never add access rights beyond what is specified in the <b>DesiredAccess</b> member. If the access right is listed as a modifiable flag, the access right can be removed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557745">ObjectPreCallback</a>
 

 

