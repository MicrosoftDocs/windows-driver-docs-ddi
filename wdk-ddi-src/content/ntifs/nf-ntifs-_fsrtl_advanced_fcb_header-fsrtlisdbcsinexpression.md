---
UID: NF:ntifs.FsRtlIsDbcsInExpression
title: FsRtlIsDbcsInExpression function (ntifs.h)
description: The FsRtlIsDbcsInExpression routine determines whether an ANSI or double-byte character set (DBCS) string matches the specified pattern.
old-location: ifsk\fsrtlisdbcsinexpression.htm
tech.root: ifsk
ms.assetid: 87292b33-4b82-4ac5-b71b-523391e5fea2
ms.date: 04/16/2018
keywords: ["FsRtlIsDbcsInExpression function"]
ms.keywords: FsRtlIsDbcsInExpression, FsRtlIsDbcsInExpression routine [Installable File System Drivers], fsrtlref_f38a4fe0-8553-4e19-a6c9-fb83a81c6cb5.xml, ifsk.fsrtlisdbcsinexpression, ntifs/FsRtlIsDbcsInExpression
f1_keywords:
 - "ntifs/FsRtlIsDbcsInExpression"
 - "FsRtlIsDbcsInExpression"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlIsDbcsInExpression
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlIsDbcsInExpression function


## -description


The <b>FsRtlIsDbcsInExpression</b> routine determines whether an ANSI or double-byte character set (DBCS) string matches the specified pattern. 


## -parameters




### -param Expression [in]

A pointer to the pattern string. Can contain wildcard characters. 


### -param Name [in]

A pointer to the string to be compared against the pattern. Cannot contain wildcard characters. 


## -returns



<b>FsRtlIsDbcsInExpression</b> returns <b>TRUE</b> if the string matches the pattern, <b>FALSE</b> otherwise.




## -remarks



The following wildcard characters can be used in the pattern string.

<table>
<tr>
<th>Wildcard Character</th>
<th>Meaning</th>
</tr>
<tr>
<td>
* (asterisk)

</td>
<td>
Matches zero or more characters.

</td>
</tr>
<tr>
<td>
? (question mark)

</td>
<td>
Matches a single character.

</td>
</tr>
<tr>
<td>
ANSI_DOS_DOT

</td>
<td>
Matches either a period or zero characters beyond the name string.

</td>
</tr>
<tr>
<td>
ANSI_DOS_QM

</td>
<td>
Matches any single character or, upon encountering a period or end of name string, advances the expression to the end of the set of contiguous ANSI_DOS_QMs.

</td>
</tr>
<tr>
<td>
ANSI_DOS_STAR

</td>
<td>
Matches zero or more characters until encountering and matching the final . in the name.

</td>
</tr>
</table>
 

Pattern matching is case sensitive. To perform a case-insensitive match, the caller must use a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlupperstring">RtlUpperString</a> to convert the pattern and input strings to uppercase before calling <b>FsRtlIsDbcsInExpression</b>.

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisnameinexpression">FsRtlIsNameInExpression</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlupperstring">RtlUpperString</a>
 

 

