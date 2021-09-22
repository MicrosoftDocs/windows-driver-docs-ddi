---
UID: NS:ntifs._ATOMIC_CREATE_ECP_CONTEXT
title: ATOMIC_CREATE_ECP_CONTEXT (ntifs.h)
description: This structure allows supplemental operations to be performed on a file atomically during create.
old-location: ifsk\atomic_create_ecp_context.htm
tech.root: ifsk
ms.date: 09/09/2021
keywords: ["ATOMIC_CREATE_ECP_CONTEXT structure"]
ms.keywords: "*PATOMIC_CREATE_ECP_CONTEXT, ATOMIC_CREATE_ECP_CONTEXT, ATOMIC_CREATE_ECP_CONTEXT structure [Installable File System Drivers], ATOMIC_CREATE_ECP_IN_FLAG_BEST_EFFORT, ATOMIC_CREATE_ECP_IN_FLAG_EOF_SPECIFIED, ATOMIC_CREATE_ECP_IN_FLAG_OPERATION_MASK, ATOMIC_CREATE_ECP_IN_FLAG_REPARSE_POINT_SPECIFIED, ATOMIC_CREATE_ECP_IN_FLAG_SPARSE_SPECIFIED, ATOMIC_CREATE_ECP_IN_FLAG_VDL_SPECIFIED, ATOMIC_CREATE_ECP_OUT_FLAG_EOF_SET, ATOMIC_CREATE_ECP_OUT_FLAG_OPERATION_MASK, ATOMIC_CREATE_ECP_OUT_FLAG_REPARSE_POINT_SET, ATOMIC_CREATE_ECP_OUT_FLAG_SPARSE_SET, ATOMIC_CREATE_ECP_OUT_FLAG_VDL_SET, PATOMIC_CREATE_ECP_CONTEXT, PATOMIC_CREATE_ECP_CONTEXT structure pointer [Installable File System Drivers], _ATOMIC_CREATE_ECP_CONTEXT, ifsk.atomic_create_ecp_context, ntifs/ATOMIC_CREATE_ECP_CONTEXT, ntifs/PATOMIC_CREATE_ECP_CONTEXT"
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: ATOMIC_CREATE_ECP_CONTEXT, *PATOMIC_CREATE_ECP_CONTEXT
f1_keywords:
 - _ATOMIC_CREATE_ECP_CONTEXT
 - ntifs/_ATOMIC_CREATE_ECP_CONTEXT
 - PATOMIC_CREATE_ECP_CONTEXT
 - ntifs/PATOMIC_CREATE_ECP_CONTEXT
 - ATOMIC_CREATE_ECP_CONTEXT
 - ntifs/ATOMIC_CREATE_ECP_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _ATOMIC_CREATE_ECP_CONTEXT
 - PATOMIC_CREATE_ECP_CONTEXT
 - ATOMIC_CREATE_ECP_CONTEXT
---

# ATOMIC_CREATE_ECP_CONTEXT structure

## -description

The **ATOMIC_CREATE_ECP_CONTEXT** structure contains the extra create parameter (ECP) context that allows supplemental operations to be performed on a file atomically during create.

## -struct-fields

### -field Size

The size of this context structure, in bytes.

### -field InFlags

Flags that indicate the requested supplemental operation(s) to be performed with the create operation.

| Value | Meaning |
| ----- | ------- |
| ATOMIC_CREATE_ECP_IN_FLAG_SPARSE_SPECIFIED | Requests that the sparse flag be set on the file. |
| ATOMIC_CREATE_ECP_IN_FLAG_REPARSE_POINT_SPECIFIED | Requests that a reparse point be set on the file. |
| ATOMIC_CREATE_ECP_IN_FLAG_EOF_SPECIFIED | Requests that a file size be set on the file. This also implies
that on-disk allocation will occur to support the requested file size. |
| ATOMIC_CREATE_ECP_IN_FLAG_VDL_SPECIFIED | Requests that a valid data length be set on the file.  This also implies that the file size be set to at least the requested valid data length. NOTE: this is considered a privileged operation if it could potentially
expose uninitialized data. |
| ATOMIC_CREATE_ECP_IN_FLAG_OPERATION_MASK | Use this flag as a mask to specify the other **InFlags** flag values. |
| ATOMIC_CREATE_ECP_IN_FLAG_BEST_EFFORT | Indicates that the file system should perform the create operation even if some of the requested supplemental operations could not be
performed or are not supported by the file system. The caller can check **OutFlags** to see which operations were performed. If this flag is not specified, the file system should fail the create operation if it cannot successfully perform all of the requested supplemental operations. |

### -field OutFlags

Flags that indicate the actual supplemental operation(s) performed with a successful create operation.

| Value | Meaning |
| ----- | ------- |
| ATOMIC_CREATE_ECP_OUT_FLAG_SPARSE_SET | Indicates that the sparse flag was set on the file. |
| ATOMIC_CREATE_ECP_OUT_FLAG_REPARSE_POINT_SET | Indicates that a reparse point was set on the file. |
| ATOMIC_CREATE_ECP_OUT_FLAG_EOF_SET | Indicates that a file size was set on the file, and that on-disk allocation occurred to support the requested file size. |
| ATOMIC_CREATE_ECP_OUT_FLAG_VDL_SET | Indicates that a valid data length was set on the file, and that the file size was set to at least the requested valid data length. |
| ATOMIC_CREATE_ECP_OUT_FLAG_OPERATION_MASK | Use this flag value as a mask to determine the supplemental operations that were performed with the create operation. |

### -field ReparseBufferLength

The length of the **ReparseBuffer** member. This value can't exceed the **MAXIMUM_REPARSE_DATA_BUFFER_SIZE** (16K).

### -field ReparseBuffer

The optional value that indicates the type of buffer used in the create operation. Possible values are **REPARSE_DATA_BUFFER** or **REPARSE_GUID_DATA_BUFFER**.

### -field FileSize

The optional value that is used with **ATOMIC_CREATE_ECP_IN_FLAG_EOF_SPECIFIED** to indicate the requested file size to be set on the file.

### -field ValidDataLength

The optional value that is used with **ATOMIC_CREATE_ECP_IN_FLAG_VDL_SPECIFIED** to indicate the requested valid data length to be set on the file.

### -field FileTimestamps

Pointer to an optional [**FILE_TIMESTAMPS**](/previous-versions/mt826486(v=vs.85)) structure which contains the last recorded instance of specific actions on a file.

### -field FileAttributes

Specifies the attributes of a file.

### -field UsnSourceInfo

Specifies optional Update Sequence Number (USN) source info flags.

### -field Usn

Specifies the Update Sequence Number (USN). This value is filled at the end of **GUID_ECP_ATOMIC_CREATE** .

### -field SuppressFileAttributeInheritanceMask

Mask that indicates the file attributes whose normal inheritance rules should be suppressed.

### -field InOpFlags

ATOMIC_CREATE_ECP_IN_OP_FLAG_xxx flags.

### -field OutOpFlags

ATOMIC_CREATE_ECP_OUT_OP_FLAG_xxx flags.

### -field InGenFlags

ATOMIC_CREATE_ECP_IN_GN_FLAG_xxx flags.

### -field OutGenFlags

ATOMIC_CREATE_ECP_OUT_GN_FLAG_xxx flags.

### -field CaseSensitiveFlagsMask

Indicates which FILE_CS_FLAG_xxx flags are specified; file systems should pick the default values for other flags.

### -field InCaseSensitiveFlags

Input case sensitive flags on the file. Even if no BEST_EFFORT is specified, file systems can ignore some of the  InCaseSensitiveFlags. The behavior is similar to  FileCaseSensitiveInformation so callers could examine **OutCaseSensitiveFlags** to know the flags that are set. If a flag is not supported on some file or directory then BEST_EFFORT would take effect.

### -field OutCaseSensitiveFlags

This member returns the case sensitive flags on the file, even if no **InCaseSensitiveFlags** are specified.

## -remarks

The system-defined GUID_ECP_ATOMIC_CREATE** value is used with this ECP context structure when calling ECP-related support routines such as [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md) and [**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md).

See [Introduction to extra create parameters](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters) for more information.
