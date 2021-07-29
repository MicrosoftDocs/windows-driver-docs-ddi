---
UID: NF:ntifs.NtOpenProcessTokenEx
title: NtOpenProcessTokenEx function (ntifs.h)
description: The NtOpenProcessTokenEx routine opens the access token associated with a process, and returns a handle that can be used to access that token.
old-location: kernel\zwopenprocesstokenex.htm
tech.root: kernel
ms.date: 06/21/2021
keywords: ["NtOpenProcessTokenEx function"]
ms.keywords: NtOpenProcessTokenEx, ZwOpenProcessTokenEx, ZwOpenProcessTokenEx routine [Kernel-Mode Driver Architecture], k111_ab983257-9c27-4f73-af7c-d903de3a33d3.xml, kernel.zwopenprocesstokenex, ntifs/NtOpenProcessTokenEx, ntifs/ZwOpenProcessTokenEx
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NtOpenProcessTokenEx
 - ntifs/NtOpenProcessTokenEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtOpenProcessTokenEx
---

# NtOpenProcessTokenEx function

## -description

The **NtOpenProcessTokenEx** routine opens the access token associated with a process, and returns a handle that can be used to access that token.

## -parameters

### -param ProcessHandle

[in] Handle to the process whose access token is to be opened. The handle must have PROCESS_QUERY_INFORMATION access. Use the **NtCurrentProcess** macro, defined in *Ntddk.h*, to specify the current process.

### -param DesiredAccess

[in] [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list ([**DACL**](../wdm/ns-wdm-_acl.md)) to determine which accesses are granted or denied.

### -param HandleAttributes

[in] Attributes for the access token handle. Only OBJ_KERNEL_HANDLE is currently supported. If the caller is not running in the system process context, it must specify OBJ_KERNEL_HANDLE for this parameter.

### -param TokenHandle

[out] Pointer to a caller-allocated variable that receives a handle to the newly opened access token.

## -returns

**NtOpenProcessTokenEx** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED          | *ProcessHandle* did not have PROCESS_QUERY_INFORMATION access. |
| STATUS_INSUFFICIENT_RESOURCES | A new token handle could not be allocated. |
| STATUS_INVALID_HANDLE         | *ProcessHandle* was not a valid handle. |
| STATUS_INVALID_PARAMETER      | The specified *HandleAttributes* did not include OBJ_KERNEL_HANDLE.              |
| STATUS_OBJECT_TYPE_MISMATCH   | *ProcessHandle* was not a process handle. |
| STATUS_PRIVILEGE_NOT_HELD     | The caller does not have the privilege ([SeSecurityPrivilege](/windows/win32/secauthz/privilege-constants)) necessary to create a token handle with the access specified in the *DesiredAccess* parameter. |
| STATUS_QUOTA_EXCEEDED         | The process's memory quota is not sufficient to allocate the token handle. |
| STATUS_UNSUCCESSFUL           | The token handle could not be created. |

## -remarks

Any handle obtained by calling **NtOpenProcessTokenEx** must eventually be released by calling [**NtClose**](nf-ntifs-ntclose.md).

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the *HandleAttributes* parameter of **NtOpenProcessTokenEx**. This restricts the use of the handle returned by **NtOpenProcessTokenEx** to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.

For more information about security and access control, see the documentation on these topics in the Windows SDK.

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**PsDereferencePrimaryToken**](./nf-ntifs-psdereferenceprimarytoken.md)

[**NtClose**](nf-ntifs-ntclose.md)

[**NtOpenThreadTokenEx**](/previous-versions/ff567032(v=vs.85))