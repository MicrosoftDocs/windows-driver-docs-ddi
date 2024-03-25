---
UID: NF:ntifs.RtlDeleteAce
title: RtlDeleteAce function (ntifs.h)
description: Learn more about the RtlDeleteAce function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["RtlDeleteAce function"]
ms.keywords: RtlDeleteAce, RtlDeleteAce routine [Installable File System Drivers], ifsk.rtldeleteace, ntifs/RtlDeleteAce, rtlref_68fe46f1-318a-48c6-9004-c338f52f41a5.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Server 2003 SP1
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlDeleteAce
 - ntifs/RtlDeleteAce
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlDeleteAce
---

# RtlDeleteAce function

## -description

The **RtlDeleteAce** routine deletes an access control entry (ACE) from a specified access control list (ACL).

## -parameters

### -param Acl [in, out]

Pointer to the ACL to be modified. **RtlDeleteAce** deletes the specified ACE from this ACL.

### -param AceIndex [in]

Specifies the ACE to delete. A value of zero corresponds to the first ACE in the ACL, 1 to the second ACE, and so on.

## -returns

**RtlDeleteAce** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_PARAMETER | One of the parameter values was invalid. |

Possible reasons for STATUS_INVALID_PARAMETER include:

* The specified ACL is invalid.
* The specified index value is out of range.
* STATUS_INVALID_PARAMETER is an error code.

## -remarks

For information about calculating the size of an ACL, see the Remarks section of the reference entry for [**RtlCreateAcl**](nf-ntifs-rtlcreateacl.md).

To add an ACE to an ACL, use [**RtlAddAce**](nf-ntifs-rtladdace.md).

To obtain a pointer to an ACE in an ACL, use [**RtlGetAce**](nf-ntifs-rtlgetace.md).

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**ACE**](/windows-hardware/drivers/ifs/ace)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**RtlAddAce**](nf-ntifs-rtladdace.md)

[**RtlCreateAcl**](nf-ntifs-rtlcreateacl.md)

[**RtlGetAce**](nf-ntifs-rtlgetace.md)
