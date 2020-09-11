---
UID: NF:ntifs.FsRtlDissectDbcs
title: FsRtlDissectDbcs function (ntifs.h)
description: Given an ANSI or double-byte character set (DBCS) pathname string, the FsRtlDissectDbcs routine returns two strings:\_one containing the first file name found in the string, the other containing the remaining unparsed portion of the pathname string.
old-location: ifsk\fsrtldissectdbcs.htm
tech.root: ifsk
ms.assetid: c5c400af-9e59-4cf0-b66f-985fcdcbc75c
ms.date: 04/16/2018
keywords: ["FsRtlDissectDbcs function"]
ms.keywords: FsRtlDissectDbcs, FsRtlDissectDbcs routine [Installable File System Drivers], fsrtlref_95d6ca19-1a11-4fc9-85a5-ea3cf307d2d0.xml, ifsk.fsrtldissectdbcs, ntifs/FsRtlDissectDbcs
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlDissectDbcs
 - ntifs/FsRtlDissectDbcs
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlDissectDbcs
dev_langs:
 - c++
---

# FsRtlDissectDbcs function


## -description

Given an ANSI or double-byte character set (DBCS) pathname string, the <b>FsRtlDissectDbcs</b> routine returns two strings: one containing the first file name found in the string, the other containing the remaining unparsed portion of the pathname string.

## -parameters

### -param Path 

[in]
The pathname string to be parsed.

### -param FirstName 

[out]
A pointer to the first file name in the pathname string.

### -param RemainingName 

[out]
A pointer to the remaining unparsed portion of the pathname string.

## -remarks

In the input string, backslashes are read as name separators. The first name in the string is assumed to consist of all characters from the beginning of the string to the character preceding the first backslash, inclusive. There is just one exception to this rule: if the first character in the input string is a backslash, this character is ignored and does not appear in the output string. The remaining portion of the string consists of all characters following the backslash that follows the first name found in the string. 

<b>FsRtlDissectDbcs</b> does not check for the presence of illegal characters in the input string.

The following table shows sample input and output values for <b>FsRtlDissectDbcs</b>:

<table>
<tr>
<th>Path</th>
<th>FirstName</th>
<th>RemainingName</th>
</tr>
<tr>
<td>
empty

</td>
<td>
empty

</td>
<td>
empty

</td>
</tr>
<tr>
<td>
A

</td>
<td>
A

</td>
<td>
empty

</td>
</tr>
<tr>
<td>
A\B\C\D\E

</td>
<td>
A

</td>
<td>
B\C\D\E

</td>
</tr>
<tr>
<td>
*A?

</td>
<td>
*A?

</td>
<td>
empty

</td>
</tr>
<tr>
<td>
\A

</td>
<td>
A

</td>
<td>
empty

</td>
</tr>
<tr>
<td>
A[,]

</td>
<td>
A[,]

</td>
<td>
empty

</td>
</tr>
<tr>
<td>
A\\B+;\C

</td>
<td>
A

</td>
<td>
\B+;\C

</td>
</tr>
</table>
 

Note that upon returning, the <b>Buffer</b> members of the output parameters will point into the <b>Buffer</b> member of <b>Path</b>.  Therefore, the caller should not allocate storage for the <b>Buffer</b> members of the two output parameters, as shown in the following example:


```
.
.
.
/*
The FsRtlDissectDbcs routine will set the members
of the following two structures appropriately:
*/
UNICODE_STRING CurrentComponent;
UNICODE_STRING RemainingComponent;

/*
Do not allocate storage for the Buffer members of CurrentComponent
and RemainingComponent in that they will point into the previoulsy
allocated storage of FullPathName's Buffer member:
*/
FsRtlDissectDbcs (FullPathName, &CurrentComponent, &RemainingComponent);
.
.
.
```

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>.

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>

