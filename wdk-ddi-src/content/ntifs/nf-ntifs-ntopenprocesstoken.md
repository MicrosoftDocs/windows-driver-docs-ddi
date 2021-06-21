---
UID: NF:ntifs.NtOpenProcessToken
tech.root: kernel
title: NtOpenProcessToken function (ntifs.h)
ms.date: 06/21/2021
targetos: Windows
description: The NtOpenProcessToken routine opens the access token associated with a process, and returns a handle that can be used to access that token.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - NtOpenProcessToken
f1_keywords:
 - NtOpenProcessToken
 - ntifs/NtOpenProcessToken
dev_langs:
 - c++
---

## -description

The **NtOpenProcessToken** routine opens the access token associated with a process, and returns a handle that can be used to access that token.

## -parameters

### -param ProcessHandle

[in] Handle to the process whose access token is to be opened. The handle must have PROCESS_QUERY_INFORMATION access. Use the **NtCurrentProcess** macro, defined in *Ntddk.h*, to specify the current process.

### -param DesiredAccess

[in] [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list ([**DACL**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl)) to determine which accesses are granted or denied.

### -param TokenHandle

[out] Pointer to a caller-allocated variable that receives a handle to the newly opened access token.

## -returns

**NtOpenProcessToken** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED          | *ProcessHandle* did not have PROCESS_QUERY_INFORMATION access. |
| STATUS_INSUFFICIENT_RESOURCES | A new token handle could not be allocated. |
| STATUS_INVALID_HANDLE         | *ProcessHandle* was not a valid handle. |
| STATUS_OBJECT_TYPE_MISMATCH   | *ProcessHandle* was not a process handle. |
| STATUS_PRIVILEGE_NOT_HELD     | The caller does not have the privilege ([SeSecurityPrivilege](/windows/win32/secauthz/privilege-constants)) necessary to create a token handle with the access specified in the *DesiredAccess* parameter. |
| STATUS_QUOTA_EXCEEDED         | The process's memory quota is not sufficient to allocate the token handle. |
| STATUS_UNSUCCESSFUL           | The token handle could not be created. |

## -remarks

To specify attributes for the access token handle, use [**NtOpenProcessTokenEx**](nf-ntifs-ntopenprocesstokenex.md) instead.

The handle can be accessed by the process in whose context the driver is running.

Any handle obtained by calling **NtOpenProcessToken** must eventually be released by calling [**NtClose**](nf-ntifs-ntclose.md).

For more information about security and access control, see the documentation on these topics in the Windows SDK.

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask)

[**ACL**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl)

[**PsDereferencePrimaryToken**](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceprimarytoken)

[**NtClose**](nf-ntifs-ntclose.md)

[**NtOpenProcessTokenEx**](nf-ntifs-ntopenprocesstokenex.md)

[**NtOpenThreadTokenEx**](/previous-versions/ff567032(v=vs.85))
