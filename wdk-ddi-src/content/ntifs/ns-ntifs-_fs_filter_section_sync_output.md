---
UID: NS:ntifs._FS_FILTER_SECTION_SYNC_OUTPUT
title: "_FS_FILTER_SECTION_SYNC_OUTPUT"
author: windows-driver-content
description: The FS_FILTER_SECTION_SYNC_OUTPUT structure contains information describing the attributes of the section that is being created.
old-location: ifsk\fs_filter_section_sync_output_.htm
old-project: ifsk
ms.assetid: 3378D971-B5D8-485B-8C58-BE5874445407
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PFS_FILTER_SECTION_SYNC_OUTPUT, ,, C, E, F, FS_FILTER_SECTION_SYNC_OUTPUT, FS_FILTER_SECTION_SYNC_OUTPUT structure [Installable File System Drivers], I, L, N, O, P, PFS_FILTER_SECTION_SYNC_OUTPUT, PFS_FILTER_SECTION_SYNC_OUTPUT structure pointer [Installable File System Drivers], R, S, T, U, Y, _, _FS_FILTER_SECTION_SYNC_OUTPUT, ifsk.fs_filter_section_sync_output_, ntifs/FS_FILTER_SECTION_SYNC_OUTPUT, ntifs/PFS_FILTER_SECTION_SYNC_OUTPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FS_FILTER_SECTION_SYNC_OUTPUT
product: Windows
targetos: Windows
req.typenames: FS_FILTER_SECTION_SYNC_OUTPUT, *PFS_FILTER_SECTION_SYNC_OUTPUT
---

# _FS_FILTER_SECTION_SYNC_OUTPUT structure


## -description


The  <b>FS_FILTER_SECTION_SYNC_OUTPUT</b> structure contains information describing the attributes of the section that is being created.


## -syntax


````
typedef struct _FS_FILTER_SECTION_SYNC_OUTPUT  {
  ULONG StructureSize;
  ULONG SizeReturned;
  ULONG Flags;
  ULONG DesiredReadAlignment;
} FS_FILTER_SECTION_SYNC_OUTPUT , *PFS_FILTER_SECTION_SYNC_OUTPUT ;
````


## -struct-fields




### -field StructureSize

The size of the structure.


### -field SizeReturned

The size of the structure which has been successfully populated with information on completion.


### -field Flags

Reserved for future use.  Should be zero.


### -field DesiredReadAlignment

Specifies the optimal size for efficient reads.  Faults from the section will attempt, but not guarantee, to read in multiples of this size.  This value should be a multiple of PAGE_SIZE.

