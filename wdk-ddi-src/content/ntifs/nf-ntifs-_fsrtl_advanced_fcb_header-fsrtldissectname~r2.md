---
UID: NF:ntifs.FsRtlDissectName~r2
title: FsRtlDissectName function (ntifs.h)
description: Given a Unicode pathname string, the FsRtlDissectName routine returns two strings, one containing the first file name found in the string, the other containing the remaining unparsed portion of the pathname string.
old-location: ifsk\fsrtldissectname.htm
tech.root: ifsk
ms.assetid: d97de0e1-0724-485d-95da-b9811036a21e
ms.date: 03/29/2018
ms.keywords: FsRtlDissectName, FsRtlDissectName routine [Installable File System Drivers], fsrtlref_a74da803-0994-46e4-90f7-bc7728b59fe5.xml, ifsk.fsrtldissectname, ntifs/FsRtlDissectName
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlDissectName"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlDissectName
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlDissectName function


## -description


Given a Unicode pathname string, the <b>FsRtlDissectName</b> routine returns two strings, one containing the first file name found in the string, the other containing the remaining unparsed portion of the pathname string.


## -parameters




### -param Path [in]

Pathname string to be parsed.


### -param FirstName [out]

Pointer to the first file name in the pathname string.


### -param RemainingName [out]

Pointer to the remaining unparsed portion of the pathname string.


## -returns



None




## -remarks



In the input string, backslashes are read as name separators. The first name in the string is assumed to consist of all characters from the beginning of the string to the character preceding the first backslash, inclusive. There is just one exception to this rule: if the first character in the input string is a backslash, this character is ignored and does not appear in the output string. The remaining portion of the string consists of all characters following the backslash that follows the first name found in the string.

<b>FsRtlDissectName</b> does not check for the presence of illegal characters in the input string.

The following table shows sample input and output values for <b>FsRtlDissectName</b>.

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

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>.
.
.
/*
The FsRtlDissectName routine will set the members
of the following two structures appropriately:
*/
UNICODE_STRING CurrentComponent;
UNICODE_STRING RemainingComponent;

/*
Do not allocate storage for the Buffer members of CurrentComponent
and RemainingComponent in that they will point into the previoulsy
allocated storage of FullPathName's Buffer member:
*/
FsRtlDissectName (FullPathName, &CurrentComponent, &RemainingComponent);
.
.
.</pre>
</td>
</tr>
</table></span></div>
For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Strings</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

