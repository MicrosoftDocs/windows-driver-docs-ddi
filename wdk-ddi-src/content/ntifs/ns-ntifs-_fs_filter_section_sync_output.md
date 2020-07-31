---
UID: NS:ntifs._FS_FILTER_SECTION_SYNC_OUTPUT
title: _FS_FILTER_SECTION_SYNC_OUTPUT (ntifs.h)
description: The FS_FILTER_SECTION_SYNC_OUTPUT structure contains information describing the attributes of the section that is being created.
old-location: ifsk\fs_filter_section_sync_output_.htm
tech.root: ifsk
ms.assetid: 3378D971-B5D8-485B-8C58-BE5874445407
ms.date: 04/16/2018
keywords: ["_FS_FILTER_SECTION_SYNC_OUTPUT structure"]
ms.keywords: "*PFS_FILTER_SECTION_SYNC_OUTPUT, FS_FILTER_SECTION_SYNC_OUTPUT, FS_FILTER_SECTION_SYNC_OUTPUT structure [Installable File System Drivers], PFS_FILTER_SECTION_SYNC_OUTPUT, PFS_FILTER_SECTION_SYNC_OUTPUT structure pointer [Installable File System Drivers], _FS_FILTER_SECTION_SYNC_OUTPUT, ifsk.fs_filter_section_sync_output_, ntifs/FS_FILTER_SECTION_SYNC_OUTPUT, ntifs/PFS_FILTER_SECTION_SYNC_OUTPUT"
f1_keywords:
 - "ntifs/FS_FILTER_SECTION_SYNC_OUTPUT"
 - "FS_FILTER_SECTION_SYNC_OUTPUT"
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FS_FILTER_SECTION_SYNC_OUTPUT
targetos: Windows
req.typenames: FS_FILTER_SECTION_SYNC_OUTPUT, *PFS_FILTER_SECTION_SYNC_OUTPUT
---

# _FS_FILTER_SECTION_SYNC_OUTPUT structure


## -description


The  <b>FS_FILTER_SECTION_SYNC_OUTPUT</b> structure contains information describing the attributes of the section that is being created.


## -struct-fields


### -field StructureSize

The size of the structure.


### -field SizeReturned

The size of the structure which has been successfully populated with information on completion.


### -field Flags

Specifies the support for synchronization. The following values can be used:

| Name | Value | 
| -- | -- |
| FS_FILTER_SECTION_SYNC_SUPPORTS_ASYNC_PARALLEL_IO | 0x00000001 |
| FS_FILTER_SECTION_SYNC_SUPPORTS_DIRECT_MAP_DATA | 0x00000002 |
| FS_FILTER_SECTION_SYNC_SUPPORTS_DIRECT_MAP_IMAGE | 0x00000004 |



### -field DesiredReadAlignment

Specifies the optimal size for efficient reads.  Faults from the section will attempt, but not guarantee, to read in multiples of this size.  This value should be a multiple of PAGE_SIZE.

