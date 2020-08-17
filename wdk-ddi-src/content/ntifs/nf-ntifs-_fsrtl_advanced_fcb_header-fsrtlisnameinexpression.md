---
UID: NF:ntifs.FsRtlIsNameInExpression
title: FsRtlIsNameInExpression function (ntifs.h)
description: The FsRtlIsNameInExpression routine determines whether a Unicode string matches the specified pattern.
old-location: ifsk\fsrtlisnameinexpression.htm
tech.root: ifsk
ms.assetid: 8d54bf46-dc70-47a1-a391-6e32a7800a9e
ms.date: 06/27/2019
keywords: ["FsRtlIsNameInExpression function"]
ms.keywords: FsRtlIsNameInExpression, FsRtlIsNameInExpression routine [Installable File System Drivers], fsrtlref_719072fe-274b-482a-ba9c-4a21d4d2be21.xml, ifsk.fsrtlisnameinexpression, ntifs/FsRtlIsNameInExpression
f1_keywords:
 - "ntifs/FsRtlIsNameInExpression"
 - "FsRtlIsNameInExpression"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available in Windows 2000 and later versions of the Windows operating system.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlIsNameInExpression
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlIsNameInExpression function

## -description

The **FsRtlIsNameInExpression** routine determines whether a Unicode string matches the specified pattern.

## -parameters

### -param Expression 
[in]
A pointer to the pattern string. Can contain wildcard characters. If *IgnoreCase* is **TRUE**, *Expression* must be uppercase.

### -param Name 
[in]
A pointer to the string to be compared against the pattern. Cannot contain wildcard characters.

### -param IgnoreCase 
[in]
Set to **TRUE** for case-insensitive matching, **FALSE** otherwise.

### -param UpcaseTable 
[in, optional]
Optional pointer to uppercase character table to use for case-insensitive matching. If this value is not supplied, the default system uppercase character table is used.

## -returns

**FsRtlIsNameInExpression** returns **TRUE** if the string matches the pattern, **FALSE** otherwise.

## -remarks

The following wildcard characters can be used in the pattern string.

| Wildcard character | Meaning |
| ------------------ | ------- |
| * (asterisk) | Matches zero or more characters. |
| ? (question mark) | Matches a single character. |
| DOS_DOT | Matches either a period or zero characters beyond the name string. |
| DOS_QM | Matches any single character or, upon encountering a period or end of name string, advances the expression to the end of the set of contiguous DOS_QMs. |
| DOS_STAR | Matches zero or more characters until encountering and matching the final . in the name. |

In low resource conditions, **FsRtlIsNameInExpression** can raise a structured exception with a code of STATUS_NO_MEMORY, which callers should be prepared to handle. For more information, see [Structured Exception Handling](https://docs.microsoft.com/windows/win32/debug/structured-exception-handling).

> [!NOTE]
> If only one of the string parameters has a length of zero, **FsRtlIsNameInExpression** returns **FALSE**. This means that "*" does not match a null string.
>
> If both parameters are null strings, **FsRtlIsNameInExpression** returns **TRUE**.

## -see-also

[**FsRtlIsDbcsInExpression**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisdbcsinexpression)

[UNICODE_STRING](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
