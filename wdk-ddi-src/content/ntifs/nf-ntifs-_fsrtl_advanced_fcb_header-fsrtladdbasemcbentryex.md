---
UID: NF:ntifs.FsRtlAddBaseMcbEntryEx
title: FsRtlAddBaseMcbEntryEx function (ntifs.h)
description: The FsRtlAddBaseMcbEntryEx function is used to add a new mapping of virtual block numbers (VBN's) to logical block numbers (LBN's) to an existing map control block (MCB).
ms.assetid: a99ea591-5af1-410a-9aa3-89839b4330bc
tech.root: ifsk
ms.date: 10/19/2018
keywords: ["FsRtlAddBaseMcbEntryEx function"]
f1_keywords:
 - "ntifs/FsRtlAddBaseMcbEntryEx"
 - "FsRtlAddBaseMcbEntryEx"
ms.keywords: FsRtlAddBaseMcbEntryEx
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
- FsRtlAddBaseMcbEntryEx
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlAddBaseMcbEntryEx function


## -description

The FsRtlAddBaseMcbEntryEx function is used to add a new mapping of virtual block numbers (VBN's) to logical block numbers (LBN's) to an existing map control block (MCB).

## -parameters

### -param Mcb

Supplies the Mcb in which to add the new mapping.

### -param Vbn

Supplies the starting VBN of the new mapping run to add to the Mcb.

### -param Lbn

Supplies the starting Lbn of the new mapping run to add to the Mcb.

### -param SectorCount
Supplies the size of the new mapping run (in sectors).

## -returns
This function returns one of the following NTSTATUS values:

Status|Meaning
---|----
STATUS_SUCCESSFUL|the mapping was added successfully (i.e., the new VBNs did not collide with existing VBNs),
STATUS_INSUFFICIENT_RESOURCES|There wasn't memory to add the new mapping.
STATUS_UNSUCCESSFULL|There was a collision with the new VBN's and existing VBN's.

## -remarks

The mapping for the VBNs must not already exist in the Mcb.  If the
mapping continues a previous run, then this routine will actually coalesce
them into 1 run.

If pool is not available to store the information this routine will raise a
status value indicating insufficient resources.

An input Lbn value of zero is illegal (i.e., the Mcb structure will never
map a VBN to a zero Lbn value).

## -see-also
