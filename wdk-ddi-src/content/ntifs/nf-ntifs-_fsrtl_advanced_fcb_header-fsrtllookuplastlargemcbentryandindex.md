---
UID: NF:ntifs.FsRtlLookupLastLargeMcbEntryAndIndex
title: FsRtlLookupLastLargeMcbEntryAndIndex function (ntifs.h)
description: Learn more about the FsRtlLookupLastLargeMcbEntryAndIndex function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlLookupLastLargeMcbEntryAndIndex function"]
ms.keywords: FsRtlLookupLastLargeMcbEntryAndIndex, FsRtlLookupLastLargeMcbEntryAndIndex routine [Installable File System Drivers], fsrtlref_d7148458-8a3c-4633-8be3-578623ba4d01.xml, ifsk.fsrtllookuplastlargemcbentryandindex, ntifs/FsRtlLookupLastLargeMcbEntryAndIndex
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlLookupLastLargeMcbEntryAndIndex
 - ntifs/FsRtlLookupLastLargeMcbEntryAndIndex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlLookupLastLargeMcbEntryAndIndex
dev_langs:
 - c++
---

# FsRtlLookupLastLargeMcbEntryAndIndex function

## -description

The **FsRtlLookupLastLargeMcbEntryAndIndex** routine retrieves the last mapping entry stored in a given map control block (MCB).

## -parameters

### -param OpaqueMcb [in]

Pointer to an initialized MCB structure to be searched.

### -param LargeVbn [out]

Pointer to a variable that receives the last virtual block number (VBN) that was mapped.

### -param LargeLbn [out]

Pointer to a variable that receives the logical block number (LBN) that is mapped to the VBN pointed to by **LargeVbn**, or -1 if no such LBN exists.

### -param Index [out]

Pointer to a variable that receives the index of the last run in the MCB.

## -returns

**FsRtlLookupLastLargeMcbEntryAndIndex** returns FALSE if the MCB contains no mapping entries, FALSE otherwise.

## -remarks

**FsRtlLookupLastLargeMcbEntryAndIndex** searches for the last mapping of the last run in the MCB:

* If the MCB contains no mappings, **FsRtlLookupLastLargeMcbEntryAndIndex** returns FALSE.

* If the last mapping is a hole, **FsRtlLookupLastLargeMcbEntryAndIndex** returns FALSE, but the lookup operation yields a value of -1 for the LBN.

* If the last mapping is not a hole, the lookup operation yields a positive value for the LBN, and **FsRtlLookupLastLargeMcbEntryAndIndex** returns FALSE.

The upper 32 bits of the LBN are ignored. Only the lower 32 bits are used.

## -see-also

[**FsRtlAddLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry.md)

[**FsRtlGetNextLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry.md)

[**FsRtlInitializeLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb.md)

[**FsRtlLookupLastLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry.md)

[**FsRtlNumberOfRunsInLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md)

[**FsRtlRemoveLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry.md)

[**FsRtlSplitLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb.md)

[**FsRtlTruncateLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb.md)

[**FsRtlUninitializeLargeMcb**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md)
