---
UID: NS:ntddk._PS_CREATE_NOTIFY_INFO
title: PS_CREATE_NOTIFY_INFO (ntddk.h)
description: The PS_CREATE_NOTIFY_INFO structure provides information about a newly created process.
tech.root: kernel
ms.date: 12/08/2022
keywords: ["PS_CREATE_NOTIFY_INFO structure"]
ms.keywords: "*PPS_CREATE_NOTIFY_INFO, PPS_CREATE_NOTIFY_INFO, PPS_CREATE_NOTIFY_INFO structure pointer [Kernel-Mode Driver Architecture], PS_CREATE_NOTIFY_INFO, PS_CREATE_NOTIFY_INFO structure [Kernel-Mode Driver Architecture], _PS_CREATE_NOTIFY_INFO, kernel.ps_create_notify_info, kstruct_c_489ee208-518d-41f1-af90-a8873f3e7fb0.xml, ntddk/PPS_CREATE_NOTIFY_INFO, ntddk/PS_CREATE_NOTIFY_INFO"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt:
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
 - _PS_CREATE_NOTIFY_INFO
 - PPS_CREATE_NOTIFY_INFO
 - PS_CREATE_NOTIFY_INFO
---

## -description

The **PS_CREATE_NOTIFY_INFO** structure provides information about a newly created process.

## -struct-fields

### -field Size

The size, in bytes, of this structure. The operating system uses this size to indicate the type of structure that it passes to [CreateProcessNotifyEx](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine). Currently, this member is always **sizeof**(**PS_CREATE_NOTIFY_INFO**).

### -field Flags

Reserved. Use the **FileOpenNameAvailable** member instead.

### -field FileOpenNameAvailable

A Boolean value that specifies whether the **ImageFileName** member contains the exact file name that is used to open the process executable file.

### -field IsSubsystemProcess

A Boolean value that indicates the type of process subsystem is a subsystem other than Win32.

**IsSubsystemProcess** is only populated for subsystem processes other than Win32 when a driver has registered through [PsSetCreateProcessNotifyRoutineEx2](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutineex2) with a type that allows for notifications from subsystem processes.  When **IsSubsystemProcess** is set, the **FileObject**, **ImageFileName**, and **CommandLine** may be NULL.  Drivers should use **ProcessSubsystemInformation** to query the subsystem type if needed.

For more information, see [NtQueryInformationProcess](/windows/win32/api/winternl/nf-winternl-ntqueryinformationprocess).

### -field Reserved

Reserved for system use.

### -field ParentProcessId

The process ID of the parent process for the new process. Note that the parent process is not necessarily the same process as the process that created the new process. The new process can inherit certain properties of the parent process, such as handles or shared memory. (The process ID of the process creator is given by **CreatingThreadId**->**UniqueProcess**.)

### -field CreatingThreadId

The process ID and thread ID of the process and thread that created the new process. **CreatingThreadId**->**UniqueProcess** contains the process ID, and **CreatingThreadId**->**UniqueThread** contains the thread ID.

### -field FileObject

A pointer to the file object for the process executable file.

If **IsSubsystemProcess** is TRUE, this value may be **NULL**.

### -field ImageFileName

A pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) string that holds the file name of the executable. If the **FileOpenNameAvailable** member is **TRUE**, the string specifies the exact file name that is used to open the executable file. If **FileOpenNameAvailable** is **FALSE**, the operating system might provide only a partial name.

If **IsSubsystemProcess** is TRUE, this value maybe NULL.

### -field CommandLine

A pointer to a **UNICODE_STRING** string that holds the command that is used to execute the process. If the command is not available, **CommandLine** is **NULL**.

If **IsSubsystemProcess** is TRUE, this value maybe NULL.

### -field CreationStatus

The NTSTATUS value to return for the process-creation operation. Drivers can change this value to an error code to prevent the process from being created.

## -see-also

[CreateProcessNotifyEx](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine)

[PsSetCreateProcessNotifyRoutineEx](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutineex)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
