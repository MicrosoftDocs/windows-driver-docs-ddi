---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlIsNameInExpression~r3
title: FsRtlIsNameInExpression function
author: windows-driver-content
description: The FsRtlIsNameInExpression routine determines whether a Unicode string matches the specified pattern.
old-location: ifsk\fsrtlisnameinexpression.htm
old-project: ifsk
ms.assetid: 8d54bf46-dc70-47a1-a391-6e32a7800a9e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlIsNameInExpression
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available in Windows 2000 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlIsNameInExpression
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# FsRtlIsNameInExpression function



## -description
The <b>FsRtlIsNameInExpression</b> routine determines whether a Unicode string matches the specified pattern. 



## -syntax

````
BOOLEAN FsRtlIsNameInExpression(
  _In_     PUNICODE_STRING Expression,
  _In_     PUNICODE_STRING Name,
  _In_     BOOLEAN         IgnoreCase,
  _In_opt_ PWCH            UpcaseTable
);
````


## -parameters

### -param Expression [in]

A pointer to the pattern string. Can contain wildcard characters. If <i>IgnoreCase</i> is <b>TRUE</b>, <i>Expression</i> must be uppercase. 


### -param Name [in]

A pointer to the string to be compared against the pattern. Cannot contain wildcard characters. 


### -param IgnoreCase [in]

Set to <b>TRUE</b> for case-insensitive matching, <b>FALSE</b> otherwise.


### -param UpcaseTable [in, optional]

Optional pointer to uppercase character table to use for case-insensitive matching. If this value is not supplied, the default system uppercase character table is used.


## -returns
<b>FsRtlIsNameInExpression</b> returns <b>TRUE</b> if the string matches the pattern, <b>FALSE</b> otherwise.


## -remarks
The following wildcard characters can be used in the pattern string.

* (asterisk)

Matches zero or more characters.

? (question mark)

Matches a single character.

DOS_DOT

Matches either a period or zero characters beyond the name string.

DOS_QM

Matches any single character or, upon encountering a period or end of name string, advances the expression to the end of the set of contiguous DOS_QMs.

DOS_STAR

Matches zero or more characters until encountering and matching the final . in the name.
<p class="note">If both parameters are null strings, <b>FsRtlIsNameInExpression</b> returns <b>TRUE</b>.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisdbcsinexpression~r1.md">FsRtlIsDbcsInExpression</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsNameInExpression routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

