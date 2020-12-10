---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegalHpfs
title: FsRtlIsAnsiCharacterLegalHpfs macro (ntifs.h)
description: The FsRtlIsAnsiCharacterLegalHpfs macro determines whether an ANSI character is legal for HPFS file names.
old-location: ifsk\fsrtlisansicharacterlegalhpfs.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIsAnsiCharacterLegalHpfs macro"]
ms.keywords: FsRtlIsAnsiCharacterLegalHpfs, FsRtlIsAnsiCharacterLegalHpfs function [Installable File System Drivers], fsrtlref_063585f7-66ed-427f-aaea-c19d9d10fb5c.xml, ifsk.fsrtlisansicharacterlegalhpfs, ntifs/FsRtlIsAnsiCharacterLegalHpfs
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlIsAnsiCharacterLegalHpfs
 - ntifs/FsRtlIsAnsiCharacterLegalHpfs
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlIsAnsiCharacterLegalHpfs
---

# FsRtlIsAnsiCharacterLegalHpfs macro


## -description

The <b>FsRtlIsAnsiCharacterLegalHpfs</b> macro determines whether an ANSI character is legal for HPFS file names.

## -parameters

### -param C

<p>Pointer to the character to be tested.</p>

### -param WILD_OK

<p>Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.</p>

## -remarks

For information about other string-handling routines, see <a href="/windows-hardware/drivers/ddi/_kernel/#run-time-library-rtl-routines">Run-Time Library (RTL) Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegal">FsRtlIsAnsiCharacterLegal</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalfat">FsRtlIsAnsiCharacterLegalFat</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalntfs">FsRtlIsAnsiCharacterLegalNtfs</a>
