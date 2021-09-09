---
UID: NF:ntifs.NtOpenThreadTokenEx
title: NtOpenThreadTokenEx function (ntifs.h)
description: The NtOpenThreadTokenEx routine opens the access token associated with a thread.
old-location: kernel\zwopenthreadtokenex.htm
tech.root: kernel
ms.date: 06/21/2021
keywords: ["NtOpenThreadTokenEx function"]
ms.keywords: NtOpenThreadTokenEx, ZwOpenThreadTokenEx, ZwOpenThreadTokenEx routine [Kernel-Mode Driver Architecture], k111_657ad702-595c-4422-99be-ca8ecc428bbe.xml, kernel.zwopenthreadtokenex, ntifs/NtOpenThreadTokenEx, ntifs/ZwOpenThreadTokenEx
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
 - NtOpenThreadTokenEx
 - ntifs/NtOpenThreadTokenEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtOpenThreadTokenEx
---

# NtOpenThreadTokenEx function

## -description

The **NtOpenThreadTokenEx** routine opens the access token associated with a thread.

## -parameters

### -param ThreadHandle

[in] Handle to the thread whose access token is to be opened. The handle must have THREAD_QUERY_INFORMATION access. Use the **NtCurrentThread** macro to specify the current thread.

### -param DesiredAccess

[in] [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list ([**DACL**](../wdm/ns-wdm-_acl.md)) to determine which access rights are granted or denied.

### -param OpenAsSelf

[in] Boolean value specifying whether the access check is to be made against the security context of the thread calling **NtOpenThreadTokenEx** or against the security context of the process for the calling thread.

If this parameter is **FALSE**, the access check is performed using the security context for the calling thread. If the thread is impersonating a client, this security context can be that of a client process. If this parameter is **TRUE**, the access check is made using the security context of the process for the calling thread.

### -param HandleAttributes

[in] Attributes for the created handle. Only OBJ_KERNEL_HANDLE is currently supported. If the caller is not running in the system process context, it must specify OBJ_KERNEL_HANDLE for this parameter.

### -param TokenHandle

[out] Pointer to a caller-allocated variable that receives a handle to the newly opened access token.

## -returns

**NtOpenThreadTokenEx** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED |
**ThreadHandle** did not have THREAD_QUERY_INFORMATION access. |
| STATUS_CANT_OPEN_ANONYMOUS | The client requested the SecurityAnonymous impersonation level. However, an anonymous token cannot be opened. For more information, see [**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md). |
| STATUS_INVALID_HANDLE | **ThreadHandle** was not a valid handle. |
| STATUS_INVALID_PARAMETER | The specified **HandleAttributes** did not include OBJ_KERNEL_HANDLE. |
| STATUS_NO_TOKEN | An attempt has been made to open a token associated with a thread that is not currently impersonating a client. |
| STATUS_OBJECT_TYPE_MISMATCH | **ThreadHandle** was not a thread handle. |

## -remarks

**NtOpenThreadTokenEx** opens the access token associated with a thread and returns a handle for that token.

The **OpenAsSelf** parameter allows a server process to open the access token for a client process when the client process has specified the SecurityIdentification impersonation level for the **SECURITY_IMPERSONATION_LEVEL** enumerated type. Without this parameter, the calling process is not able to open the client's access token using the client's security context because it is impossible to open executive-level objects using the SecurityIdentification impersonation level.

Any handle obtained by calling **NtOpenThreadTokenEx** must eventually be released by calling **NtClose**.

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the **HandleAttributes** parameter of **NtOpenThreadTokenEx**. This restricts the use of the handle returned by **NtOpenThreadTokenEx** to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.

For more information about security and access control, see the documentation on these topics in the Windows SDK.

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**PsDereferencePrimaryToken**](./nf-ntifs-psdereferenceprimarytoken.md)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)

[**ZwClose**](./nf-ntifs-ntclose.md)

[**ZwOpenProcessTokenEx**](/previous-versions/ff567024(v=vs.85))