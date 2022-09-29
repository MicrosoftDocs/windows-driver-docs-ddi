---
UID: NF:ntifs.SecLookupAccountSid
title: SecLookupAccountSid function (ntifs.h)
description: SecLookupAccountSid accepts a security identifier (SID) as input. It retrieves the name of the account for this SID and the name of the first domain on which this SID is found.
old-location: ifsk\seclookupaccountsid.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["SecLookupAccountSid function"]
ms.keywords: SecLookupAccountSid, SecLookupAccountSid function [Installable File System Drivers], ifsk.seclookupaccountsid, ksecddref_ba65e59c-5c9a-47bb-bf2c-9b3b8c727bb6.xml, ntifs/SecLookupAccountSid
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
 - SecLookupAccountSid
 - ntifs/SecLookupAccountSid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ksecdd.lib
 - Ksecdd.dll
api_name:
 - SecLookupAccountSid
---

# SecLookupAccountSid function

## -description

**SecLookupAccountSid** accepts a security identifier (SID) as input. It retrieves the name of the account for this SID and the name of the first domain on which this SID is found.

## -parameters

### -param Sid [in]

A pointer to the SID to look up.

### -param NameSize [out]

A pointer to a variable that specifies the size of the **NameBuffer**. On input, this value specifies the size in bytes of the input **NameBuffer**. If the function fails because the buffer is too small, this variable receives the required buffer size. On success, this variable contains the size of the returned **NameBuffer**.

### -param NameBuffer [in, out]

A pointer to a buffer that receives the name of the account associated with the **Sid**. If this parameter is NULL, **NameSize** will be zero.

### -param DomainSize [out]

A pointer to a ULONG that specifies the size of the **DomainBuffer** parameter. If the function fails because the buffer is too small, this variable receives the required buffer size. If the **DomainBuffer** parameter is **NULL**, this parameter will be set to be zero.

### -param DomainBuffer [out, optional]

A pointer to a buffer that receives the name of the first domain on which this SID is found.

### -param NameUse [out]

A pointer to a [**SID_NAME_USE**](ne-ntifs-_sid_name_use.md) enumerated type that receives the type of the account.

## -returns

**SecLookupAccountSid** returns STATUS_SUCCESS on success or one of the following error codes on failure.

| Return code | Description |
| ----------- | ----------- |
| SEC_E_INTERNAL_ERROR | An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. |
| STATUS_ACCESS_DENIED | The process ID associated with the currently executing thread does not match the current process ID. |
| STATUS_BUFFER_TOO_SMALL | The buffer size for the **NameBuffer** or the **ReferencedDomain** parameter was too small. |
| STATUS_INVALID_PARAMETER | The length of the **Name** parameter exceeded the length allowed in a message to the Local System Authority (LSA). |
| STATUS_NO_MEMORY | It was not possible to allocate sufficient memory for a temporary internal buffer used by this function. |
| STATUS_NONE_MAPPED | The **Sid** parameter could not be found. |
| STATUS_PROCESS_IS_TERMINATING | This process has terminated so it is not possible to establish a local procedure call (LPC) connection. |

## -remarks

**SecLookupAccountSid** attempts to find a name for the specified SID by first checking a list of well-known SIDs. If the supplied SID does not correspond to a well-known SID, the function checks built-in and administratively defined local accounts. Next, the function checks the primary domain. Security identifiers not recognized by the primary domain are checked against the trusted domains that correspond to their SID prefixes.

If the function cannot find an account name for the SID, **SecLookupAccountSid** fails. This can occur if a network time-out prevents the function from finding the name. It also occurs for SIDs that have no corresponding account name, such as a logon SID that identifies a logon session.

In addition to looking up SIDs for local accounts, local domain accounts, and explicitly trusted domain accounts, **SecLookupAccountSid** can look up SIDs for any account in any domain in the forest, including SIDs that appear only in the SIDhistory field of an account in the forest. The SIDhistory field stores former SIDs of an account that has been moved from another domain. To look up a SID, **SecLookupAccountSid** queries the global catalog of the forest.

**SecLookupAccountSid** is equivalent to the Win32 **LookupAccountSid** function.

**SecLookupAccountSid** is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. **SecLookupAccountSid** cannot be used during paging file I/O.

## -see-also

[**SID**](ns-ntifs-_sid.md)

[**SID_NAME_USE**](ne-ntifs-_sid_name_use.md)

[**SecLookupAccountName**](nf-ntifs-seclookupaccountname.md)

[**SecLookupWellKnownSid**](nf-ntifs-seclookupwellknownsid.md)
