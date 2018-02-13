---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlDissectDbcs~r2
title: FsRtlDissectDbcs function
author: windows-driver-content
description: Given an ANSI or double-byte character set (DBCS) pathname string, the FsRtlDissectDbcs routine returns two strings:\_one containing the first file name found in the string, the other containing the remaining unparsed portion of the pathname string.
old-location: ifsk\fsrtldissectdbcs.htm
old-project: ifsk
ms.assetid: c5c400af-9e59-4cf0-b66f-985fcdcbc75c
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FsRtlDissectDbcs routine [Installable File System Drivers], fsrtlref_95d6ca19-1a11-4fc9-85a5-ea3cf307d2d0.xml, FsRtlDissectDbcs, ifsk.fsrtldissectdbcs, ntifs/FsRtlDissectDbcs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlDissectDbcs
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlDissectDbcs function


## -description


Given an ANSI or double-byte character set (DBCS) pathname string, the <b>FsRtlDissectDbcs</b> routine returns two strings: one containing the first file name found in the string, the other containing the remaining unparsed portion of the pathname string.


## -syntax


````
VOID FsRtlDissectDbcs(
  _In_  ANSI_STRING  Path,
  _Out_ PANSI_STRING FirstName,
  _Out_ PANSI_STRING RemainingName
);
````


## -parameters




### -param Path [in]

The pathname string to be parsed.


### -param FirstName [out]

A pointer to the first file name in the pathname string. 


### -param RemainingName [out]

A pointer to the remaining unparsed portion of the pathname string.


## -returns



None




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
FsRtlDissectDbcs (FullPathName, &amp;CurrentComponent, &amp;RemainingComponent);
.
.
.</pre>
</td>
</tr>
</table></span></div>
For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlDissectDbcs routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

