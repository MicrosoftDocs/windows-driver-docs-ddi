---
UID: NF:ntifs.FsRtlIsFatDbcsLegal~r3
title: FsRtlIsFatDbcsLegal function (ntifs.h)
description: The FsRtlIsFatDbcsLegal routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal FAT file name.
old-location: ifsk\fsrtlisfatdbcslegal.htm
tech.root: ifsk
ms.assetid: 1ba94491-718b-41bf-bc22-2d99ba34c6af
ms.date: 03/29/2018
keywords: ["FsRtlIsFatDbcsLegal function"]
ms.keywords: FsRtlIsFatDbcsLegal, FsRtlIsFatDbcsLegal routine [Installable File System Drivers], fsrtlref_259cf46c-3d21-4acb-9674-f858bacbee1d.xml, ifsk.fsrtlisfatdbcslegal, ntifs/FsRtlIsFatDbcsLegal
f1_keywords:
 - "ntifs/FsRtlIsFatDbcsLegal"
 - "FsRtlIsFatDbcsLegal"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlIsFatDbcsLegal
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsFatDbcsLegal function


## -description


The <b>FsRtlIsFatDbcsLegal</b> routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal FAT file name.


## -parameters




### -param DbcsName [in]

A pointer to the string to be tested.


### -param WildCardsPermissible [in]

Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.


### -param PathNamePermissible [in]

Set to <b>TRUE</b> if <i>DbcsName</i> can be a full pathname containing backslash characters, <b>FALSE</b> if it can only be file name.


### -param LeadingBackslashPermissible [in]

Set to <b>TRUE</b> if a single leading backslash is permissible in the file or pathname, <b>FALSE</b> otherwise.


## -returns



The <b>FsRtlIsFatDbcsLegal</b> routine returns <b>TRUE</b> if the string is a legal FAT file name, <b>FALSE</b> otherwise.




## -remarks



The <b>FsRtlIsFatDbcsLegal</b> routine determines whether the specified file name conforms to the FAT-specific rules for legal file names. This routine will check the file name or, if <i>PathNamePermissible</i> is specified as <b>TRUE</b>, whether the whole pathname is a legal FAT name.

FAT file names must obey the following rules:

<ul>
<li>
The following characters are illegal in FAT file names: 0x00-0x1F, " (straight quotation marks), / (slash), : (colon), | (vertical bar or pipe), + (plus), , (comma), ; (semicolon), = (equal sign), [ ] (brackets)

</li>
<li>
A FAT file name is either of the form N.E or just N, where N is a string of one to eight bytes and E is a string of one to three bytes conformant to rule one. In addition, neither N nor E may contain a . (period) or end with a space character. For example, the files ".foo", "foo.", and "foo .b" are illegal, while "foo. b" and " bar" are legal.

</li>
<li>
FAT file names are case insensitive. Lowercase names are automatically converted to uppercase.

</li>
</ul>
For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>
 

 

