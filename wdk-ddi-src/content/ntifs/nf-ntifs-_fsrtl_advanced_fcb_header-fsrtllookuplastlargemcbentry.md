---
UID: NF:ntifs.FsRtlLookupLastLargeMcbEntry
title: FsRtlLookupLastLargeMcbEntry function (ntifs.h)
description: Learn more about the FsRtlLookupLastLargeMcbEntry function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlLookupLastLargeMcbEntry function"]
ms.keywords: FsRtlLookupLastLargeMcbEntry, FsRtlLookupLastLargeMcbEntry routine [Installable File System Drivers], fsrtlref_71f4bede-0097-4707-a30e-d09c540f507f.xml, ifsk.fsrtllookuplastlargemcbentry, ntifs/FsRtlLookupLastLargeMcbEntry
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
 - FsRtlLookupLastLargeMcbEntry
 - ntifs/FsRtlLookupLastLargeMcbEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlLookupLastLargeMcbEntry
dev_langs:
 - c++
---

# FsRtlLookupLastLargeMcbEntry function

## -description

The **FsRtlLookupLastLargeMcbEntry** routine retrieves the last mapping entry stored in the map control block (MCB).

## -parameters

### -param Mcb

Pointer to an initialized MCB structure to be searched.

### -param Vbn

Pointer to a variable that receives the last virtual block number (VBN) that was mapped.

### -param Lbn

Pointer to a variable that receives the logical block number (LBN) that is mapped to the VBN pointed to by **LargeVbn**, or -1 if no such LBN exists.

## -returns

**FsRtlLookupLastLargeMcbEntry** returns FALSE if the MCB contains no mapping entries, TRUE otherwise.

## -remarks

**FsRtlLookupLastLargeMcbEntry** searches for the last mapping of the last run in the MCB:

* If the MCB contains no mappings, **FsRtlLookupLastLargeMcbEntry** returns FALSE.

* If the last mapping is a hole, **FsRtlLookupLastLargeMcbEntry** returns TRUE, but the lookup operation yields a value of -1 for the LBN.

* If the last mapping is not a hole, the lookup operation yields a positive value for the LBN, and **FsRtlLookupLastLargeMcbEntry** returns TRUE.

The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used.

## -see-also

[**FsRtlAddLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry.md)

[**FsRtlGetNextLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry.md)

[**FsRtlInitializeLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb.md)

[**FsRtlLookupLastLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry.md)

[**FsRtlLookupLastLargeMcbEntryAndIndex**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex.md)

[**FsRtlNumberOfRunsInLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md)

[**FsRtlRemoveLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry.md)

[**FsRtlSplitLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb.md)

[**FsRtlTruncateLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb.md)

[**FsRtlUninitializeLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md)
