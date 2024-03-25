---
UID: NF:ntifs.RtlAddAce
title: RtlAddAce function (ntifs.h)
description: Learn more about the RtlAddAce function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["RtlAddAce function"]
ms.keywords: RtlAddAce, RtlAddAce routine [Installable File System Drivers], ifsk.rtladdace, ntifs/RtlAddAce, rtlref_798d31d8-c233-4154-981d-a84cfdd95045.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Server 2003 with SP1
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlAddAce
 - ntifs/RtlAddAce
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlAddAce
---

# RtlAddAce function

## -description

The **RtlAddAce** routine adds one or more access control entries (ACEs) to a specified access control list ([**ACL**](../wdm/ns-wdm-_acl.md)).

## -parameters

### -param Acl [in, out]

Pointer to the ACL to be modified. **RtlAddAce** adds the specified ACEs to this ACL.

### -param AceRevision [in]

ACL revision level of the ACE to be added. Windows version requirments are the following:

| Value | Meaning |
| ----- | ------- |
| ACL_REVISION    | The revision level valid on all Windows versions. |
| ACL_REVISION_DS | The revision level valid starting with Windows 2000. |

**AceRevision** must be ACL_REVISION_DS if the ACL in **Acl** contains an object-specific ACE.

### -param StartingAceIndex [in]

Specifies the position in the ACL's list of ACEs at which to add new ACEs. A value of zero inserts the ACEs at the beginning of the list. A value of MAXULONG appends the ACEs to the end of the list.

### -param AceList [in]

Pointer to a buffer containing a list of one or more ACEs to be added to the specified ACL. The ACEs in the list must be stored contiguously.

### -param AceListLength [in]

Size, in bytes, of the input buffer pointed to by the **AceList** parameter.

## -returns

**RtlAddAce** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_BUFFER_TOO_SMALL   | The new ACEs do not fit into the ACL. A larger ACL buffer is required. STATUS_BUFFER_TOO_SMALL is an error code. |
| STATUS_INVALID_PARAMETER | One of the parameter values was invalid. Possible reasons include that the specified ACL is invalid or the specified revision is unknown, is not compatible with revisions in the ACE list, or is not compatible with the revision of the ACL. STATUS_INVALID_PARAMETER is an error code. |

## -remarks

For information about calculating the size of an ACL, see the Remarks section of the reference entry for [**RtlCreateAcl**](nf-ntifs-rtlcreateacl.md).

To obtain a pointer to an ACE in an ACL, use [**RtlGetAce**](nf-ntifs-rtlgetace.md).

To delete an ACE from an ACL, use [**RtlDeleteAce**](nf-ntifs-rtldeleteace.md).

To add an access-allowed ACE to an ACL, use [**RtlAddAccessAllowedAce**](nf-ntifs-rtladdaccessallowedace.md).

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**ACE**](/windows-hardware/drivers/ifs/ace)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**RtlAddAccessAllowedAce**](nf-ntifs-rtladdaccessallowedace.md)

[**RtlCreateAcl**](nf-ntifs-rtlcreateacl.md)

[**RtlDeleteAce**](nf-ntifs-rtldeleteace.md)

[**RtlGetAce**](nf-ntifs-rtlgetace.md)
