---
UID: NF:ntifs.NtOpenThreadToken
tech.root: kernel
title: NtOpenThreadToken
ms.date: 10/06/2022
targetos: Windows
description: The NtOpenThreadToken routine opens the access token associated with a thread, and returns a handle that can be used to access that token.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows XP
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
 - NtOpenThreadToken
f1_keywords:
 - NtOpenThreadToken
 - ntifs/NtOpenThreadToken
dev_langs:
 - c++
ms.custom: engagement-fy23
---

## -description

The **NtOpenThreadToken** routine opens the access token associated with a thread, and returns a handle that can be used to access that token.

## -parameters

### -param ThreadHandle [in]

Handle to the thread whose access token is to be opened. The handle must have THREAD_QUERY_INFORMATION access. Use the **NtCurrentThread** macro to specify the current thread.

### -param DesiredAccess [in]

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) structure specifying the requested types of access to the access token. These requested access types are compared with the token's discretionary access-control list ([**DACL**](../wdm/ns-wdm-_acl.md)) to determine which access rights are granted or denied.

### -param OpenAsSelf [in]

Boolean value specifying whether the access check is to be made against the security context of the thread calling **NtOpenThreadToken** or against the security context of the process for the calling thread.

If this parameter is **FALSE**, the access check is performed using the security context for the calling thread. If the thread is impersonating a client, this security context can be that of a client process. If this parameter is **TRUE**, the access check is made using the security context of the process for the calling thread.

### -param TokenHandle [out]

Pointer to a caller-allocated variable that receives a handle to the newly opened access token.

## -returns

**NtOpenThreadToken** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED |
**ThreadHandle** did not have THREAD_QUERY_INFORMATION access. |
| STATUS_CANT_OPEN_ANONYMOUS | The client requested the SecurityAnonymous impersonation level. However, an anonymous token cannot be opened. For more information, see [**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md). |
| STATUS_INVALID_HANDLE | **ThreadHandle** was not a valid handle. |
| STATUS_NO_TOKEN | An attempt has been made to open a token associated with a thread that is not currently impersonating a client. |
| STATUS_OBJECT_TYPE_MISMATCH | **ThreadHandle** was not a thread handle. |

## -remarks

**NtOpenThreadToken** opens the access token associated with a thread and returns a handle for that token.

The **OpenAsSelf** parameter allows a server process to open the access token for a client process when the client process has specified the SecurityIdentification impersonation level for the **SECURITY_IMPERSONATION_LEVEL** enumerated type. Without this parameter, the calling process is not able to open the client's access token using the client's security context because it is impossible to open executive-level objects using the SecurityIdentification impersonation level.

Any handle obtained by calling **NtOpenThreadToken** must eventually be released by calling **NtClose**.

For more information about security and access control, see the documentation on these topics in the Windows SDK.

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**NtOpenThreadTokenEx**](nf-ntifs-ntopenthreadtokenex.md)

[**PsDereferencePrimaryToken**](./nf-ntifs-psdereferenceprimarytoken.md)

[**SECURITY_IMPERSONATION_LEVEL**](../wdm/ne-wdm-_security_impersonation_level.md)

[**ZwClose**](nf-ntifs-ntclose.md)

[**ZwOpenProcessTokenEx**](nf-ntifs-zwopenprocesstokenex.md)
