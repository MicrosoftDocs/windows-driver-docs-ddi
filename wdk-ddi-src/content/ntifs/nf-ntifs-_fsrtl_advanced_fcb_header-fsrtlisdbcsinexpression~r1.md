---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlIsDbcsInExpression~r1
title: FsRtlIsDbcsInExpression function
author: windows-driver-content
description: The FsRtlIsDbcsInExpression routine determines whether an ANSI or double-byte character set (DBCS) string matches the specified pattern.
old-location: ifsk\fsrtlisdbcsinexpression.htm
old-project: ifsk
ms.assetid: 87292b33-4b82-4ac5-b71b-523391e5fea2
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ntifs/FsRtlIsDbcsInExpression, fsrtlref_f38a4fe0-8553-4e19-a6c9-fb83a81c6cb5.xml, ifsk.fsrtlisdbcsinexpression, FsRtlIsDbcsInExpression, FsRtlIsDbcsInExpression routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlIsDbcsInExpression
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsDbcsInExpression function


## -description


The <b>FsRtlIsDbcsInExpression</b> routine determines whether an ANSI or double-byte character set (DBCS) string matches the specified pattern. 


## -syntax


````
BOOLEAN FsRtlIsDbcsInExpression(
  _In_ PANSI_STRING Expression,
  _In_ PANSI_STRING Name
);
````


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
 

Pattern matching is case sensitive. To perform a case-insensitive match, the caller must use a routine such as <a href="..\ntddk\nf-ntddk-rtlupperstring.md">RtlUpperString</a> to convert the pattern and input strings to uppercase before calling <b>FsRtlIsDbcsInExpression</b>.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="..\ntddk\nf-ntddk-rtlupperstring.md">RtlUpperString</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisnameinexpression~r3.md">FsRtlIsNameInExpression</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsDbcsInExpression routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

