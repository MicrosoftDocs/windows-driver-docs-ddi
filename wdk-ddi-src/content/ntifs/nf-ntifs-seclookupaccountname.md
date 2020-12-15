---
UID: NF:ntifs.SecLookupAccountName
title: SecLookupAccountName function (ntifs.h)
description: SecLookupAccountName accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found.
old-location: ifsk\seclookupaccountname.htm
tech.root: ifsk
ms.date: 04/16/2018
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

<b>SecLookupAccountName</b> accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found.

## -parameters

### -param Name 

[in]
A pointer to a Unicode string that specifies the account name. Use a fully qualified string in the domain_name\user_name format to ensure that <b>SecLookupAccountName</b> finds the account in the desired domain.

### -param SidSize 

[in, out]
A pointer to a variable that specifies the size of the <i>Sid</i> buffer. On input, this value specifies the size in bytes of the input <i>Sid</i> buffer. If the function fails because the buffer is too small or if <i>SidSize</i> is zero, this variable receives the required buffer size. On success, this variable contains the size of the returned <i>Sid</i>.

### -param Sid 

[out]
A pointer to a buffer that receives the SID structure that corresponds to the account name pointed to by the <i>Name</i> parameter. If this parameter is <b>NULL</b>, <i>SidSize</i> must be zero.

### -param NameUse 

[out]
A pointer to a SID_NAME_USE enumerated type that indicates the type of the account when the function returns.

### -param OPTIONAL

<p>A pointer to an optional variable that specifies the size of the <i>ReferencedDomain</i> parameter. On input, this value specifies the size of the <i>ReferencedDomain</i> buffer. If the function fails because the buffer is too small, this variable receives the required buffer size. If the <i>ReferencedDomain</i> parameter is <b>NULL</b>, this parameter must be zero.</p>

## -returns

<b>SecLookupAccountName</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SEC_E_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The process ID associated with the currently executing thread does not match the current process ID. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer size for the <i>Sid</i> or the <i>ReferencedDomain</i> parameter was too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The length of the <i>Name</i> parameter exceeded the length allowed in a message to the Local System Authority. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NONE_MAPPED</b></dt>
</dl>
</td>
<td width="60%">
The <i>Name</i> parameter could not be found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
This process has terminated so it is not possible to establish the local procedure call (LPC) connection.

</td>
</tr>
</table>

## -remarks

<b>SecLookupAccountName</b> attempts to find a SID for the specified name. The function checks built-in and administratively defined local accounts. Next, the function checks the primary domain. If the name is not found there, trusted domains are checked.

Use fully qualified account names (for example, domain_name\user_name) instead of isolated names (for example, user_name). Fully qualified names are unambiguous and provide better performance when the lookup is performed. This function also supports fully qualified DNS names (for example, example.example.com\user_name) and user principal names (UPN) (for example, someone@example.com).

In addition to looking up local accounts, local domain accounts, and explicitly trusted domain accounts, <b>SecLookupAccountName</b> can look up the name for any account in any domain in the forest.

<b>SecLookupAccountName</b> is equivalent to the Win32 <b>LookupAccountName</b> function. 

<b>SecLookupAccountName</b> is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. <b>SecLookupAccountName</b> cannot be used during paging file I/O.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_sid_name_use">SID_NAME_USE</a>



<a href="/previous-versions/ff556579(v=vs.85)">SecLookupAccountSid</a>



<a href="/previous-versions/ff556582(v=vs.85)">SecLookupWellKnownSid</a>
