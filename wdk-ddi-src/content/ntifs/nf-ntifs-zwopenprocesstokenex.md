---
UID: NF:ntifs.ZwOpenProcessTokenEx
title: ZwOpenProcessTokenEx function (ntifs.h)
description: The ZwOpenProcessTokenEx routine opens the access token associated with a process.
old-location: kernel\zwopenprocesstokenex.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["ZwOpenProcessTokenEx function"]
ms.keywords: NtOpenProcessTokenEx, ZwOpenProcessTokenEx, ZwOpenProcessTokenEx routine [Kernel-Mode Driver Architecture], k111_ab983257-9c27-4f73-af7c-d903de3a33d3.xml, kernel.zwopenprocesstokenex, ntifs/NtOpenProcessTokenEx, ntifs/ZwOpenProcessTokenEx
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
 - ZwOpenProcessTokenEx
 - ntifs/ZwOpenProcessTokenEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenProcessTokenEx
---

# ZwOpenProcessTokenEx function

## -description

The **ZwOpenProcessTokenEx** routine opens the access token associated with a process.

## -parameters

### -param ProcessHandle [in]

Handle to the process whose access token is to be opened. The handle must have PROCESS_QUERY_INFORMATION access. Use the **NtCurrentProcess** macro, defined in Ntddk.h, to specify the current process.

### -param DesiredAccess [in]

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list ([**DACL**](../wdm/ns-wdm-_acl.md)) to determine which accesses are granted or denied.

### -param HandleAttributes [in]

Attributes for the access token handle. Only OBJ_KERNEL_HANDLE is currently supported. If the caller is not running in the system process context, it must specify OBJ_KERNEL_HANDLE for this parameter.

### -param TokenHandle [out]

Pointer to a caller-allocated variable that receives a handle to the newly opened access token.

## -returns

**ZwOpenProcessTokenEx** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED | **ProcessHandle** did not have PROCESS_QUERY_INFORMATION access. |
| STATUS_INSUFFICIENT_RESOURCES | A new token handle could not be allocated. |
| STATUS_INVALID_HANDLE | **ProcessHandle** was not a valid handle. |
| STATUS_INVALID_PARAMETER | The specified **HandleAttributes** did not include OBJ_KERNEL_HANDLE. |
| STATUS_OBJECT_TYPE_MISMATCH | **ProcessHandle** was not a process handle. |
| STATUS_PRIVILEGE_NOT_HELD | The caller does not have the privilege (SeSecurityPrivilege) necessary to create a token handle with the access specified in the **DesiredAccess** parameter. |
| STATUS_QUOTA_EXCEEDED | The process's memory quota is not sufficient to allocate the token handle. |
| STATUS_UNSUCCESSFUL | The token handle could not be created. |

## -remarks

**ZwOpenProcessTokenEx** opens the access token associated with a process and returns a handle for that token.

Any handle obtained by calling **ZwOpenProcessTokenEx** must eventually be released by calling **ZwClose**.

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the **HandleAttributes** parameter of **ZwOpenProcessTokenEx**. This restricts the use of the handle returned by **ZwOpenProcessTokenEx** to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.

For more information about security and access control, see the documentation on these topics in the Windows SDK.

> [!NOTE]
> If the call to the **ZwOpenProcessTokenEx** function occurs in user mode, you should use the name "**NtOpenProcessTokenEx**" instead of "**ZwOpenProcessTokenEx**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**PsDereferencePrimaryToken**](nf-ntifs-psdereferenceprimarytoken.md)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**ZwClose**](../wdm/nf-wdm-zwclose.md)

[**ZwOpenThreadTokenEx**](nf-ntifs-zwopenthreadtokenex.md)
