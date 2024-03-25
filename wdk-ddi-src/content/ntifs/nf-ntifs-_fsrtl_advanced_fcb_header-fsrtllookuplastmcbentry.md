---
UID: NF:ntifs.FsRtlLookupLastMcbEntry
title: FsRtlLookupLastMcbEntry function (ntifs.h)
description: Learn more about the FsRtlLookupLastMcbEntry function.
tech.root: ifsk
ms.date: 10/06/2023
keywords: ["FsRtlLookupLastMcbEntry function"]
ms.keywords: FsRtlLookupLastMcbEntry, FsRtlLookupLastMcbEntry function [Installable File System Drivers], fsrtlref_432dcb48-ee5d-4eef-89ee-d10e6e8a9da7.xml, ifsk.fsrtllookuplastmcbentry, ntifs/FsRtlLookupLastMcbEntry
req.header: ntifs.h
req.include-header: Ntifs.h
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlLookupLastMcbEntry
 - ntifs/FsRtlLookupLastMcbEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlLookupLastMcbEntry
dev_langs:
 - c++
---

# FsRtlLookupLastMcbEntry function

## -description

The **FsRtlLookupLastMcbEntry** routine retrieves the last mapping entry stored in the map control block (MCB). It's obsolete, but is exported to support existing driver binaries. Use [**FsRtlLookupLastLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry.md) instead.

## -parameters

### -param Mcb

Reserved.

### -param Vbn

Reserved.

### -param Lbn

Reserved.

## -returns

**FsRtlGetNextLargeMcbEntry** returns TRUE if the requested mapping run exists in the MCB, FALSE otherwise.
