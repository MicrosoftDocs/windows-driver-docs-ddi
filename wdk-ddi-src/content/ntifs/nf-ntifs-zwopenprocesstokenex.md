---
UID: NF:ntifs.ZwOpenProcessTokenEx
title: ZwOpenProcessTokenEx function (ntifs.h)
description: The ZwOpenProcessTokenEx routine opens the access token associated with a process.
old-location: kernel\zwopenprocesstokenex.htm
tech.root: kernel
ms.assetid: 2ea6f764-b884-4764-a2ff-19d0170f9b31
ms.date: 04/30/2018
ms.keywords: NtOpenProcessTokenEx, ZwOpenProcessTokenEx, ZwOpenProcessTokenEx routine [Kernel-Mode Driver Architecture], k111_ab983257-9c27-4f73-af7c-d903de3a33d3.xml, kernel.zwopenprocesstokenex, ntifs/NtOpenProcessTokenEx, ntifs/ZwOpenProcessTokenEx
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
-	ZwOpenProcessTokenEx
-	NtOpenProcessTokenEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwOpenProcessTokenEx function


## -description


The <b>ZwOpenProcessTokenEx</b> routine opens the access token associated with a process. 


## -parameters




### -param ProcessHandle [in]

Handle to the process whose access token is to be opened. The handle must have PROCESS_QUERY_INFORMATION access. Use the <b>NtCurrentProcess</b> macro, defined in Ntddk.h, to specify the current process. 


### -param DesiredAccess [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list (<a href="https://msdn.microsoft.com/dac27df2-fabd-4402-8daf-9317888dd30b">DACL</a>) to determine which accesses are granted or denied.


### -param HandleAttributes [in]

Attributes for the access token handle. Only OBJ_KERNEL_HANDLE is currently supported. If the caller is not running in the system process context, it must specify OBJ_KERNEL_HANDLE for this parameter. 


### -param TokenHandle [out]

Pointer to a caller-allocated variable that receives a handle to the newly opened access token. 


## -returns



<b>ZwOpenProcessTokenEx</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
<i>ProcessHandle</i> did not have PROCESS_QUERY_INFORMATION access. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A new token handle could not be allocated. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>ProcessHandle</i> was not a valid handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>HandleAttributes</i> did not include OBJ_KERNEL_HANDLE. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
<i>ProcessHandle</i> was not a process handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have the privilege (SeSecurityPrivilege) necessary to create a token handle with the access specified in the <i>DesiredAccess</i> parameter. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_QUOTA_EXCEEDED</b></dt>
</dl>
</td>
<td width="60%">
The process's memory quota is not sufficient to allocate the token handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The token handle could not be created. 

</td>
</tr>
</table>
 




## -remarks



<b>ZwOpenProcessTokenEx</b> opens the access token associated with a process and returns a handle for that token. 

Any handle obtained by calling <b>ZwOpenProcessTokenEx</b> must eventually be released by calling <b>ZwClose</b>. 

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the <i>HandleAttributes</i> parameter of <b>ZwOpenProcessTokenEx</b>. This restricts the use of the handle returned by <b>ZwOpenProcessTokenEx</b> to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running. 

For more information about security and access control, see the documentation on these topics in the Windows SDK. 

<div class="alert"><b>Note</b>  If the call to the <b>ZwOpenProcessTokenEx</b> function occurs in user mode, you should use the name "<b>NtOpenProcessTokenEx</b>" instead of "<b>ZwOpenProcessTokenEx</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551896">PsDereferencePrimaryToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567032">ZwOpenThreadTokenEx</a>
 

 

