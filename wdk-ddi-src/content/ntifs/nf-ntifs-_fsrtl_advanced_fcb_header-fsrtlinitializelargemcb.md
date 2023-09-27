---
UID: NF:ntifs.FsRtlInitializeLargeMcb
title: FsRtlInitializeLargeMcb function (ntifs.h)
description: Learn more about the FsRtlInitializeLargeMcb function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlInitializeLargeMcb function"]
ms.keywords: FsRtlInitializeLargeMcb, FsRtlInitializeLargeMcb routine [Installable File System Drivers], fsrtlref_298126ca-6c2b-4662-a7ef-2dbc5d1ba361.xml, ifsk.fsrtlinitializelargemcb, ntifs/FsRtlInitializeLargeMcb
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
ms.custom: RS5
f1_keywords:
 - FsRtlInitializeLargeMcb
 - ntifs/FsRtlInitializeLargeMcb
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlInitializeLargeMcb
dev_langs:
 - c++
---

# FsRtlInitializeLargeMcb function

## -description

The **FsRtlInitializeLargeMcb** routine initializes a map control block (MCB) structure.

## -parameters

### -param Mcb

Pointer to a caller-allocated MCB structure to initialize.

### -param PoolType [in]

Type of pool to use when allocating additional internal storage for the MCB. One of the following:

* **NonPagedPool**
* **PagedPool**
* **NonPagedPoolCacheAligned**
* **PagedPoolCacheAligned**

The **NonPagedPoolMustSucceed** and **NonPagedPoolCacheAlignedMustS** pool types are obsolete and should no longer be used.

## -remarks

**FsRtlInitializeLargeMcb** initializes a map control block (MCB) structure. File systems use MCB structures to map virtual block numbers (VBN) for a file to the corresponding logical block numbers (LBN) on disk.

The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used.

File systems must call **FsRtlInitializeLargeMcb** before using any other **FsRtl*Xxx*Mcb*Yyy*** routines on the MCB structure.

If a pool allocation failure occurs, **FsRtlInitializeLargeMcb** raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to **FsRtlInitializeLargeMcb** in a *try-except* or *try-finally* statement.

## -see-also

[**FsRtlAddLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry.md)

[**FsRtlGetNextLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry.md)

[**FsRtlLookupLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry.md)

[**FsRtlLookupLastLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry.md)

[**FsRtlLookupLastLargeMcbEntryAndIndex**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex.md)

[**FsRtlNumberOfRunsInLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md)

[**FsRtlRemoveLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry.md)

[**FsRtlSplitLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb.md)

[**FsRtlTruncateLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb.md)

[**FsRtlUninitializeLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md)
