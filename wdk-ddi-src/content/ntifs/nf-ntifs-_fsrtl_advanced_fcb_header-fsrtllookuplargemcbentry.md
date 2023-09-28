---
UID: NF:ntifs.FsRtlLookupLargeMcbEntry
title: FsRtlLookupLargeMcbEntry function (ntifs.h)
description: Learn more about the FsRtlLookupLargeMcbEntry function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlLookupLargeMcbEntry function"]
ms.keywords: FsRtlLookupLargeMcbEntry, FsRtlLookupLargeMcbEntry routine [Installable File System Drivers], fsrtlref_600ea10a-a948-4169-9877-5a8a603b0426.xml, ifsk.fsrtllookuplargemcbentry, ntifs/FsRtlLookupLargeMcbEntry
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
 - FsRtlLookupLargeMcbEntry
 - ntifs/FsRtlLookupLargeMcbEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlLookupLargeMcbEntry
dev_langs:
 - c++
---

# FsRtlLookupLargeMcbEntry function

## -description

Given a virtual block number (VBN) and a map control block (MCB), the **FsRtlLookupLargeMcbEntry** routine searches the MCB for mapping information corresponding to the specified VBN.

## -parameters

### -param Mcb

Pointer to an initialized MCB structure.

### -param Vbn

Pointer to the requested VBN.

### -param Lbn

Pointer to a variable that receives the LBN that is mapped to **LargeVbn** in the mapping entry, or -1 if no such LBN exists. This parameter is optional and can be NULL.

### -param SectorCountFromLbn

Pointer to a variable that receives the number of sectors that follow **LargeVbn** in the mapping run. This parameter is optional and can be NULL.

### -param StartingLbn

Pointer to a variable that receives the LBN corresponding to the start of the mapping run, or -1 if no such LBN exists. This parameter is optional and can be NULL.

### -param SectorCountFromStartingLbn

Pointer to a variable that receives the number of sectors in the mapping run. This parameter is optional and can be NULL.

### -param Index [out, optional]

Pointer to a variable that receives the index of the mapping run that contains the VBN. This parameter is optional and can be NULL.

## -returns

**FsRtlLookupLargeMcbEntry** returns TRUE if the specified VBN is within the range of VBNs that are mapped by the MCB, FALSE otherwise.

## -remarks

**FsRtlLookupLargeMcbEntry** searches for a mapping entry in the MCB whose run includes the specified VBN.

* If such a mapping exists, the lookup operation yields positive values for the corresponding LBN and sector count, and **FsRtlLookupLargeMcbEntry** returns TRUE.

* If no such mapping exists, but the specified VBN is lower than the highest VBN mapped by the MCB, this is referred to as a hole in the mapping. In this case, **FsRtlLookupLargeMcbEntry** still returns TRUE, but the lookup operation yields a value of -1 for the LBN.

* If the specified VBN is higher than the highest VBN mapped by the MCB, or if the MCB contains no mappings, **FsRtlLookupLargeMcbEntry** returns FALSE.

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
