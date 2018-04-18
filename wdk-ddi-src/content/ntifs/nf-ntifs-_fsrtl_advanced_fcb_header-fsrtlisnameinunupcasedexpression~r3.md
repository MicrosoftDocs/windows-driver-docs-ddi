---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlIsNameInUnUpcasedExpression~r3
title: FsRtlIsNameInUnUpcasedExpression function
author: windows-driver-content
description: The FsRtlIsNameInUnUpcasedExpression routine determines whether a Unicode string matches the specified pattern.
ms.assetid: e7d84543-f480-4d05-9555-d9c4696dfe39
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: FsRtlIsNameInUnUpcasedExpression
req.header: ntifs.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.exe
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	FsRtlIsNameInUnUpcasedExpression
product: Windows
targetos: Windows

---

# FsRtlIsNameInUnUpcasedExpression function


## -description

The **FsRtlIsNameInUnUpcasedExpression** routine determines whether a Unicode string matches the specified pattern. Unlike the [FsRtlIsNameInExpression routine](https://msdn.microsoft.com/en-us/library/windows/hardware/ff546850), *FsRtlIsNameInUnUpcasedExpression* does not expect the Expression to be in upper case if *IgnoreCase* is TRUE. 

## -parameters

### -param Expression

A pointer to the pattern string. Can contain wildcard characters. If IgnoreCase is TRUE, Expression must be lowercase. 

### -param Name

A pointer to the string to be compared against the pattern. Cannot contain wildcard characters.

### -param IgnoreCase

Set to **TRUE** for case-insensitive matching, **FALSE** otherwise.

### -param UpcaseTable

Optional pointer to uppercase character table to use for case-insensitive matching. If this value is not supplied, the default system uppercase character table is used.

## -returns

Returns TRUE if the string matches the pattern, FALSE otherwise.

## -remarks

The following wildcard characters can be used in the pattern string.
Wildcard character|Meaning
------------- | -------------
* (asterisk)|Matches zero or more characters.
? (question mark)|Matches a single character.
DOS_DOT|Matches either a period or zero characters beyond the name string.
DOS_QM|Matches any single character or, upon encountering a period or end of name string, advances the expression to the end of the set of contiguous DOS_QMs.
DOS_STAR|Matches zero or more characters until encountering and matching the final . in the name.

 
**Note**  

If only one of the string parameters has a length of zero, FsRtlIsNameInUnUpcasedExpression returns FALSE. This means that "*" does not match a null string. 
If both parameters are null strings, FsRtlIsNameInUnUpcasedExpression returns TRUE.

## -see-also
- [FsRtlIsNameInExpression](https://msdn.microsoft.com/library/windows/hardware/ff546850)