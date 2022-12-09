---
UID: NF:ntddk.ZwTerminateProcess
title: ZwTerminateProcess function (ntddk.h)
description: The ZwTerminateProcess routine terminates a process and all of its threads.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["ZwTerminateProcess function"]
ms.keywords: NtTerminateProcess, ZwTerminateProcess, ZwTerminateProcess routine [Kernel-Mode Driver Architecture], k111_72c76674-5372-4662-9097-53d850d49afe.xml, kernel.zwterminateprocess, ntddk/NtTerminateProcess, ntddk/ZwTerminateProcess
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwTerminateProcess
 - ntddk/ZwTerminateProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwTerminateProcess
---

## -description

The **ZwTerminateProcess** routine terminates a process and all of its threads.

## -parameters

### -param ProcessHandle [in, optional]

A handle to the process object that represents the process to be terminated.

### -param ExitStatus [in]

An NTSTATUS value that the operating system uses as the final status for the process and each of its threads.

## -returns

**ZwTerminateProcess** returns STATUS_SUCCESS if the operation succeeds. Additional return values include:

| Return code | Description |
|---|---|
| **STATUS_OBJECT_TYPE_MISMATCH** | The specified handle is not a process handle. |
| **STATUS_INVALID_HANDLE** | The specified handle is not valid. |
| **STATUS_ACCESS_DENIED** | The driver cannot access the specified process object. |
| **STATUS_PROCESS_IS_TERMINATING** | The specified process is already terminating. |

If the caller specifies the current process in the *ProcessHandle* parameter, **ZwTerminateProcess** does not return.

## -remarks

To obtain a process handle that a driver can specify for the *ProcessHandle* parameter, the driver can call [ZwOpenProcess](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ntopenprocess). The handle must be a *kernel handle*, a handle that can only be accessed in kernel mode. A handle is a kernel handle if it is created with the OBJ_KERNEL_HANDLE flag. For more info see [InitializeObjectAttributes](/windows-hardware/drivers/ddi/wudfwdm/nf-wudfwdm-initializeobjectattributes).

Drivers must not specify the current process if resources have not been freed from the kernel stack, because the operating system will not unwind the kernel stack for the calling thread.

If the call to this function occurs in user mode, you should use the name "[NtTerminateProcess](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwterminateprocess)" instead of "**ZwTerminateProcess**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwOpenProcess](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ntopenprocess)
