---
UID: NF:ntifs.FsRtlDoesNameContainWildCards
title: FsRtlDoesNameContainWildCards function (ntifs.h)
description: The FsRtlDoesNameContainWildCards routine determines whether a Unicode string contains wildcard characters.
old-location: ifsk\fsrtldoesnamecontainwildcards.htm
tech.root: ifsk
ms.assetid: a2bcf1c0-a6c7-4bf3-bce6-9a661f2ab2e1
ms.date: 04/16/2018
keywords: ["FsRtlDoesNameContainWildCards function"]
ms.keywords: FsRtlDoesNameContainWildCards, FsRtlDoesNameContainWildCards routine [Installable File System Drivers], fsrtlref_1b39ef0b-3ec3-4d4b-9ee6-abe674e359aa.xml, ifsk.fsrtldoesnamecontainwildcards, ntifs/FsRtlDoesNameContainWildCards
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlDoesNameContainWildCards
 - ntifs/FsRtlDoesNameContainWildCards
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlDoesNameContainWildCards
---

# FsRtlDoesNameContainWildCards function


## -description

The <b>FsRtlDoesNameContainWildCards</b> routine determines whether a Unicode string contains wildcard characters.

## -parameters

### -param Name 

[in]
A pointer to the string to be checked.

## -returns

<b>FsRtlDoesNameContainWildCards</b> returns <b>TRUE</b> if one or more wildcard characters were found, <b>FALSE</b> otherwise.

## -remarks

The following are wildcard characters: *, ?, ANSI_DOS_STAR, ANSI_DOS_DOT, and ANSI_DOS_QM.

For information about other string-handling routines, see <a href="/windows-hardware/drivers/ddi/index">Strings</a>.

## -see-also

<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>