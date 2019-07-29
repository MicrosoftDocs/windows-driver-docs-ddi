---
UID: NF:ntifs.FsRtlLookupBaseMcbEntry
title: FsRtlLookupBaseMcbEntry function (ntifs.h)
description: The FsRtlLookupBaseMcbEntry routine retrieves the mapping of a Vbn to an Lbn from an Mcb. It indicates if the mapping exists and the size of the run.
ms.assetid: b997ada6-cfa2-4e3a-ae39-7f9a8c2b3234
ms.date: 10/19/2018
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlLookupBaseMcbEntry"
ms.keywords: FsRtlLookupBaseMcbEntry
req.header: ntifs.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- FsRtlLookupBaseMcbEntry
product:
- Windows
targetos: Windows

ms.custom: RS5
---

# FsRtlLookupBaseMcbEntry function


## -description


The **FsRtlLookupBaseMcbEntry** routine retrieves the mapping of a virtual block number (VBN) to a logical block number (LBN) from a map control block (MCB). It indicates if the mapping exists and the size of the run.


## -parameters

### -param Mcb
Supplies the Mcb being examined.

### -param Vbn
Supplies the Vbn to lookup.

### -param Lbn
Receives the Lbn corresponding to the Vbn.  A value of -1 is returned if the Vbn does not have a corresponding Lbn.

### -param SectorCountFromLbn
Receives the number of sectors that map from the Vbn to contiguous Lbn values beginning with the input Vbn.

### -param StartingLbn
Contains the lbn at the start of the run. If it's a hole then the starting Lbn is zero.

### -param SectorCountFromStartingLbn
Contains the number of sectors at the start of the run if a sector count argument is present.

### -param Index
Receives the index of the run found.

## -returns
This function returns TRUE if the Vbn is within the range of VBNs mapped by the MCB (even if it corresponds to a hole in the mapping), and FALSE if the Vbn is beyond the range of the MCB's mapping.

For example, if an MCB has a mapping for VBNs 5 and 7 but not for 6, then a lookup on Vbn 5 or 7 will yield a non zero Lbn and a sector count of 1.  A lookup for Vbn 6 will return TRUE with an Lbn value of 0, and lookup for Vbn 8 or above will return FALSE.

## -remarks

## -see-also
