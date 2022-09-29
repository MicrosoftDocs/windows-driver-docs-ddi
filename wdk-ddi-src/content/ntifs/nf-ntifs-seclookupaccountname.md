---
UID: NF:ntifs.SecLookupAccountName
title: SecLookupAccountName function (ntifs.h)
description: SecLookupAccountName accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found.
old-location: ifsk\seclookupaccountname.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["SecLookupAccountName function"]
ms.keywords: SecLookupAccountName, SecLookupAccountName function [Installable File System Drivers], ifsk.seclookupaccountname, ksecddref_1f4959e5-ea3b-440d-af1b-df05782eefce.xml, ntifs/SecLookupAccountName
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The SecLookupAccountName function is only available on Windows XP and later.
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
req.lib: Ksecdd.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SecLookupAccountName
 - ntifs/SecLookupAccountName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ksecdd.lib
 - Ksecdd.dll
api_name:
 - SecLookupAccountName
---

# SecLookupAccountName function

## -description

**SecLookupAccountName** accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found.

## -parameters

### -param Name [in]

A pointer to a Unicode string that specifies the account name. Use a fully qualified string in the domain_name\user_name format to ensure that **SecLookupAccountName** finds the account in the desired domain.

### -param SidSize [in, out]

A pointer to a variable that specifies the size of the **Sid** buffer. On input, this value specifies the size in bytes of the input **Sid** buffer. If the function fails because the buffer is too small or if **SidSize** is zero, this variable receives the required buffer size. On success, this variable contains the size of the returned **Sid**.

### -param Sid [out]

A pointer to a buffer that receives the SID structure that corresponds to the account name pointed to by the **Name** parameter. If this parameter is **NULL**, **SidSize** must be zero.

### -param NameUse [out]

A pointer to a [**SID_NAME_USE**](ne-ntifs-_sid_name_use.md) enumerated type that receives the type of the account.

### -param DomainSize [out]

A pointer to A ULONG that receives the size of the **ReferencedDomain** parameter. If the function fails because the buffer is too small, this variable receives the required buffer size. If the input **ReferencedDomain** parameter is NULL, this parameter will receive zero.

### -param ReferencedDomain [in_out, optional]

Pointer to a buffer for the name of the domain where the account name is found. This parameter is optional and can be NULL. For computers that are not joined to a domain, this buffer receives the computer name.

## -returns

**SecLookupAccountName** returns STATUS_SUCCESS on success or one of the following error codes on failure.

| Return code | Description |
| ----------- | ----------- |
| SEC_E_INTERNAL_ERROR | An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. |
| STATUS_ACCESS_DENIED | The process ID associated with the currently executing thread does not match the current process ID. |
| STATUS_BUFFER_TOO_SMALL | The buffer size for the **Sid** or the **ReferencedDomain** parameter was too small. |
| STATUS_INVALID_PARAMETER | The length of the **Name** parameter exceeded the length allowed in a message to the Local System Authority. |
| STATUS_NONE_MAPPED | The **Name** parameter could not be found. |
| STATUS_PROCESS_IS_TERMINATING | This process has terminated so it is not possible to establish the local procedure call (LPC) connection. |

## -remarks

**SecLookupAccountName** attempts to find a SID for the specified name. The function checks built-in and administratively defined local accounts. Next, the function checks the primary domain. If the name is not found there, trusted domains are checked.

Use fully qualified account names (for example, domain_name\user_name) instead of isolated names (for example, user_name). Fully qualified names are unambiguous and provide better performance when the lookup is performed. This function also supports fully qualified DNS names (for example, example.example.com\user_name) and user principal names (UPN) (for example, someone@example.com).

In addition to looking up local accounts, local domain accounts, and explicitly trusted domain accounts, **SecLookupAccountName** can look up the name for any account in any domain in the forest.

**SecLookupAccountName** is equivalent to the Win32 **LookupAccountName** function.

**SecLookupAccountName** is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. **SecLookupAccountName** cannot be used during paging file I/O.

## -see-also

[**SID**](ns-ntifs-_sid.md)

[**SID_NAME_USE**](ne-ntifs-_sid_name_use.md)

[**SecLookupAccountSid**](nf-ntifs-seclookupaccountsid.md)

[**SecLookupWellKnownSid**](nf-ntifs-seclookupwellknownsid.md)
