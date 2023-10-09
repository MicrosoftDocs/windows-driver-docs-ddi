---
UID: NF:ntifs.FsRtlGetNextMcbEntry
title: FsRtlGetNextMcbEntry function (ntifs.h)
description: Learn more about the FsRtlGetNextMcbEntry function.
tech.root: ifsk
ms.date: 10/06/2023
keywords: ["FsRtlGetNextMcbEntry function"]
ms.keywords: FsRtlGetNextMcbEntry, FsRtlGetNextMcbEntry function [Installable File System Drivers], fsrtlref_3465b156-f358-4049-8480-e59e92ecccbb.xml, ifsk.fsrtlgetnextmcbentry, ntifs/FsRtlGetNextMcbEntry
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
 - FsRtlGetNextMcbEntry
 - ntifs/FsRtlGetNextMcbEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlGetNextMcbEntry
dev_langs:
 - c++
---

# FsRtlGetNextMcbEntry function

## -description

The **FsRtlGetNextMcbEntry** routine retrieves a mapping run from a map control block (MCB). It's obsolete, but is exported to support existing driver binaries. Use [**FsRtlGetNextLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry.md) instead.

## -parameters

### -param Mcb

Reserved.

### -param RunIndex

Reserved.

### -param Vbn

Reserved.

### -param Lbn

Reserved.

### -param SectorCount

Reserved.

## -returns

**FsRtlGetNextMcbEntry** returns TRUE if the requested mapping run exists in the MCB; otherwise it returns FALSE.
