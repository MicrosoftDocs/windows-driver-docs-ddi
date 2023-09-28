---
UID: NF:ntifs.FsRtlIsHpfsDbcsLegal
title: FsRtlIsHpfsDbcsLegal function (ntifs.h)
description: Learn more about the FsRtlIsHpfsDbcsLegal function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FsRtlIsHpfsDbcsLegal function"]
ms.keywords: FsRtlIsHpfsDbcsLegal, FsRtlIsHpfsDbcsLegal routine [Installable File System Drivers], fsrtlref_6cde5ef1-2a54-4b66-b2da-e134b5700668.xml, ifsk.fsrtlishpfsdbcslegal, ntifs/FsRtlIsHpfsDbcsLegal
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
 - FsRtlIsHpfsDbcsLegal
 - ntifs/FsRtlIsHpfsDbcsLegal
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIsHpfsDbcsLegal
dev_langs:
 - c++
---

# FsRtlIsHpfsDbcsLegal function

## -description

The **FsRtlIsHpfsDbcsLegal** routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal HPFS file name.

## -parameters

### -param DbcsName [in]

A pointer to the string to be tested.

### -param WildCardsPermissible [in]

Set to TRUE if wildcard characters are to be considered legal, FALSE otherwise.

### -param PathNamePermissible [in]

Set to TRUE if **DbcsName** can be a full pathname containing backslash characters, FALSE if it can only be a file name.

### -param LeadingBackslashPermissible [in]

Set to TRUE if a single leading backslash is permissible in the file or pathname, FALSE otherwise.

## -returns

The **FsRtlIsHpfsDbcsLegal** routine returns TRUE if the string is a legal HPFS file name, FALSE otherwise.

## -remarks

The **FsRtlIsHpfsDbcsLegal** routine determines whether the specified file name conforms to the HPFS-specific rules for legal file names. This routine will check the file name or, if **PathNamePermissible** is specified as TRUE, whether the whole pathname is a legal HPFS name.

HPFS file names must obey the following rules:

* The following characters are illegal in HPFS file names: 0x0000 - 0x001F, " (quotation marks), / (slash), : (colon), < (less-than sign), > (greater-than sign), ? (question mark), | (vertical bar or pipe), * (asterisk)

* An HPFS file name cannot end in a period or a space. For example, the files "foo " and "foo." are illegal, while ".foo", " foo" and "foo.bar.foo" are legal.

* An HPFS file name can contain no more than 255 bytes.

* HPFS file names are case-preserving, but not case insensitive. Lowercase file names are not automatically converted to uppercase. However, case is ignored in file name comparisons.

## -see-also

[**ANSI_STRING**](/windows/win32/api/ntdef/ns-ntdef-string)
