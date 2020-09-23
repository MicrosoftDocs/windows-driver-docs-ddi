---
UID: NS:ntddk._PS_CREATE_NOTIFY_INFO
title: _PS_CREATE_NOTIFY_INFO (ntddk.h)
description: The PS_CREATE_NOTIFY_INFO structure provides information about a newly created process.
old-location: kernel\ps_create_notify_info.htm
tech.root: kernel
ms.assetid: 66fade6b-b1c1-477c-bd44-2809d02271f2
ms.date: 04/30/2018
keywords: ["PS_CREATE_NOTIFY_INFO structure"]
ms.keywords: "*PPS_CREATE_NOTIFY_INFO, PPS_CREATE_NOTIFY_INFO, PPS_CREATE_NOTIFY_INFO structure pointer [Kernel-Mode Driver Architecture], PS_CREATE_NOTIFY_INFO, PS_CREATE_NOTIFY_INFO structure [Kernel-Mode Driver Architecture], _PS_CREATE_NOTIFY_INFO, kernel.ps_create_notify_info, kstruct_c_489ee208-518d-41f1-af90-a8873f3e7fb0.xml, ntddk/PPS_CREATE_NOTIFY_INFO, ntddk/PS_CREATE_NOTIFY_INFO"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
targetos: Windows
req.typenames: PS_CREATE_NOTIFY_INFO, *PPS_CREATE_NOTIFY_INFO
f1_keywords:
 - _PS_CREATE_NOTIFY_INFO
 - ntddk/_PS_CREATE_NOTIFY_INFO
 - PPS_CREATE_NOTIFY_INFO
 - ntddk/PPS_CREATE_NOTIFY_INFO
 - PS_CREATE_NOTIFY_INFO
 - ntddk/PS_CREATE_NOTIFY_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - PS_CREATE_NOTIFY_INFO
---

# _PS_CREATE_NOTIFY_INFO structure


## -description

The <b>PS_CREATE_NOTIFY_INFO</b> structure provides information about a newly created process.

## -struct-fields

### -field Size

The size, in bytes, of this structure. The operating system uses this size to indicate the type of structure that it passes to <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">CreateProcessNotifyEx</a>. Currently, this member is always <b>sizeof</b>(<b>PS_CREATE_NOTIFY_INFO</b>).

### -field Flags

Reserved. Use the <b>FileOpenNameAvailable</b> member instead.

### -field FileOpenNameAvailable

A Boolean value that specifies whether the <b>ImageFileName</b> member contains the exact file name that is used to open the process executable file.

### -field IsSubsystemProcess

A Boolean value that indicates the type of process subsystem is a subsystem other than Win32. 

<div class="alert"><b>Note</b>  <p class="note"><b>IsSubsystemProcess</b> is only populated for subsystem processes other than Win32 when a driver has registered through <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutineex2">PsSetCreateProcessNotifyRoutineEx2</a> with a type that allows for notifications from subsystem processes.  When <b>IsSubsystemProcess</b> is set, the <b>FileObject</b>, <b>ImageFileName</b>, and <b>CommandLine</b> may be NULL.  Drivers should use <b>ProcessSubsystemInformation</b> to query the subsystem type if needed. 
For more information, see <a href="/windows/win32/api/winternl/nf-winternl-ntqueryinformationprocess">NtQueryInformationProcess</a>.

</div>
<div> </div>

### -field Reserved

Reserved for system use.

### -field ParentProcessId

The process ID of the parent process for the new process. Note that the parent process is not necessarily the same process as the process that created the new process. The new process can inherit certain properties of the parent process, such as handles or shared memory. (The process ID of the process creator is given by <b>CreatingThreadId</b>-><b>UniqueProcess</b>.)

### -field CreatingThreadId

The process ID and thread ID of the process and thread that created the new process. <b>CreatingThreadId</b>-><b>UniqueProcess</b> contains the process ID, and <b>CreatingThreadId</b>-><b>UniqueThread</b> contains the thread ID.

### -field FileObject

A pointer to the file object for the process executable file. 

<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value may be NULL. 

</div>
<div> </div>

### -field ImageFileName

A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> string that holds the file name of the executable. If the <b>FileOpenNameAvailable</b> member is <b>TRUE</b>, the string specifies the exact file name that is used to open the executable file. If <b>FileOpenNameAvailable</b> is <b>FALSE</b>, the operating system might provide only a partial name.

<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value maybe NULL. 

</div>
<div> </div>

### -field CommandLine

A pointer to a <b>UNICODE_STRING</b> string that holds the command that is used to execute the process. If the command is not available, <b>CommandLine</b> is <b>NULL</b>.

<div class="alert"><b>Note</b>  <p class="note">If <b>IsSubsystemProcess</b> is TRUE, this value maybe NULL. 

</div>
<div> </div>

### -field CreationStatus

The NTSTATUS value to return for the process-creation operation. Drivers can change this value to an error code to prevent the process from being created.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">CreateProcessNotifyEx</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutineex">PsSetCreateProcessNotifyRoutineEx</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>