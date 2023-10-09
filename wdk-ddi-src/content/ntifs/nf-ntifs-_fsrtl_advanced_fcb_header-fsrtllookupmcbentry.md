---
UID: NF:ntifs.FsRtlLookupMcbEntry
title: FsRtlLookupMcbEntry function (ntifs.h)
description: The FsRtlLookupMcbEntry function is obsolete.
old-location: ifsk\fsrtllookupmcbentry.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlLookupMcbEntry function"]
ms.keywords: FsRtlLookupMcbEntry, FsRtlLookupMcbEntry function [Installable File System Drivers], fsrtlref_2f0e31c1-e938-4e83-9547-6999c5fb8cb4.xml, ifsk.fsrtllookupmcbentry, ntifs/FsRtlLookupMcbEntry
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
 - FsRtlLookupMcbEntry
 - ntifs/FsRtlLookupMcbEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlLookupMcbEntry
dev_langs:
 - c++
---

# FsRtlLookupMcbEntry function

## -description

**FsRtlLookupMcbEntry** is obsolete, but is exported to support existing driver binaries. Use [**FsRtlLookupLargeMcbEntry**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry.md) instead.

## -parameters

### -param Mcb

Reserved.

### -param Vbn

Reserved.

### -param Lbn

Reserved.

### -param SectorCount

Reserved.

### -param Index

Reserved.

## -returns

**FsRtlLookupMcbEntry** returns TRUE if the specified VBN is within the range of VBNs that are mapped by the MCB, FALSE otherwise.
