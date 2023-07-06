---
UID: NF:ntifs.FsRtlUpperOplockFsctrl
title: FsRtlUpperOplockFsctrl function (ntifs.h)
description: Learn more about the FsRtlUpperOplockFsctrl routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FsRtlUpperOplockFsctrl function"]
ms.keywords: FsRtlUpperOplockFsctrl, OPLOCK_LEVEL_CACHE_HANDLE, OPLOCK_LEVEL_CACHE_READ, OPLOCK_LEVEL_CACHE_WRITE, ifsk.fsrtlupperoplockfsctrl, ntifs/FsRtlUpperOplockFsctrl
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
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
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlUpperOplockFsctrl
 - ntifs/FsRtlUpperOplockFsctrl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlUpperOplockFsctrl
dev_langs:
 - c++
---

# FsRtlUpperOplockFsctrl function

## -description

The **FsRtlUpperOplockFsctrl** routine processes opportunistic lock (oplock) requests and acknowledgments for secondary, or layered, file systems. The upper file system submits the state of the oplock held in the lower file system. **FsRtlUpperOplockFsctrl** will determine whether to grant or deny the upper file system oplock.

## -parameters

### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to [**FsRtlInitializeOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md).

### -param Irp [in]

A pointer to the IRP for the I/O operation.

### -param OpenCount [in]

Number of user handles for the file, if an exclusive oplock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For more information about oplock types, see [Types of Oplocks](/windows/win32/fileio/types-of-opportunistic-locks).

### -param LowerOplockState [in]

The value the lower oplock level held by the upper file system. This a bitwise OR combination of the following:

| Value | Meaning |
| ----- | ------- |
| OPLOCK_LEVEL_CACHE_READ   | Indicates an oplock Read (R) type. |
| OPLOCK_LEVEL_CACHE_WRITE  | Indicates an oplock Write (W) type. |
| OPLOCK_LEVEL_CACHE_HANDLE | Indicates an oplock Handle (H) type. |

### -param Flags [in]

A bitmask for the associated oplock operations. A file system or filter driver sets bits to specify the behavior of **FsRtlUpperOplockFsctrl**. The **Flags** parameter has the following options:

| Value | Meaning |
| ----- | ------- |
| OPLOCK_FSCTRL_FLAG_ALL_KEYS_MATCH (0x00000001) | The file system verified that all oplock keys on any currently open handles match. By specifying this flag, you allow the oplock package to grant an oplock of level RW or RWH when more than one open handle to the file exists. |

## -returns

**FsRtlUpperOplockFsctrl** returns one of the following NTSTATUS values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS            | For an IRP_MJ_CREATE request, STATUS_SUCCESS indicates that the requested filter opportunistic lock (oplock) was granted. For a FSCTL operation, the meaning of STATUS_SUCCESS depends on the FSCTL code. For more information, see the Remarks section in [**FsRtlOplockFsctrlEx**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrlex.md).  |
| STATUS_CANCELLED          | The I/O operation was canceled. STATUS_CANCELLED is an error code. |
| STATUS_INVALID_PARAMETER  | The FSCTL code for the I/O operation was not a valid values oplock request. Valid request types are listed in the Remarks section of **FsRtlOplockFsctrlEx**. STATUS_INVALID_PARAMETER is an error code.  |
| STATUS_OPLOCK_NOT_GRANTED | The oplock could not be granted. The level of the requested upper file system oplock is not valid for the oplock granted for the lower file system. STATUS_OPLOCK_NOT_GRANTED is an error code.  |
| STATUS_PENDING            | Used only for FSCTL operations. The meaning of STATUS_PENDING depends on the FSCTL code. For more information, see the Remarks section in [**FsRtlOplockFsctrlEx**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrlex.md). STATUS_PENDING is a success code. |
| STATUS_CANNOT_GRANT_REQUESTED_OPLOCK | An oplock acknowledgement for a new oplock is not allowed. The level of the upper file system of lock is not valid for the lower file system oplock. |

## -see-also

[**FsRtlCheckUpperOplock**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckupperoplock.md)

[**FsRtlOplockFsctrlEx**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrlex.md)
