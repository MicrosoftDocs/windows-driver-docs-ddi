---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAreNamesEqual~r3
title: FsRtlAreNamesEqual function
author: windows-driver-content
description: The FsRtlAreNamesEqual routine determines whether two Unicode strings are equal.
old-location: ifsk\fsrtlarenamesequal.htm
old-project: ifsk
ms.assetid: 4125e210-c3c2-475c-b516-617fca5d3d0e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlAreNamesEqual
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
req.alt-api: FsRtlAreNamesEqual
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

# FsRtlAreNamesEqual function



## -description
The <b>FsRtlAreNamesEqual</b> routine determines whether two Unicode strings are equal. 



## -syntax

````
BOOLEAN FsRtlAreNamesEqual(
  _In_     PCUNICODE_STRING ConstantNameA,
  _In_     PCUNICODE_STRING ConstantNameB,
  _In_     BOOLEAN          IgnoreCase,
  _In_opt_ PCWCH            UpcaseTable
);
````


## -parameters

### -param ConstantNameA [in]

A pointer to first string. Cannot contain wildcard characters.


### -param ConstantNameB [in]

A pointer to second string. Cannot contain wildcard characters.


### -param IgnoreCase [in]

Set to <b>TRUE</b> for case-insensitive matching, <b>FALSE</b> otherwise.


### -param UpcaseTable [in, optional]

Optional pointer to uppercase character table to use for case-insensitive matching. If this value is not supplied, the default system uppercase character table is used.


## -returns
<b>FsRtlAreNamesEqual</b> returns <b>TRUE</b> if the two Unicode strings match, <b>FALSE</b> otherwise.


## -remarks
The table pointed to by <i>UpcaseTable</i> is an array of uppercase Unicode characters, indexed by the Unicode character to be converted to uppercase. The array must contain entries for all characters that are legal in file names.

Case-insensitive matching is performed by converting both strings to uppercase before they are compared. Thus the value of <i>UpcaseTable</i>, if supplied, is used only if <i>IgnoreCase</i> is <b>TRUE</b>.

If a pool allocation failure occurs, <b>FsRtlAreNamesEqual</b> raises a STATUS_NO_MEMORY exception. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlequalunicodestring.md">RtlEqualUnicodeString</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAreNamesEqual routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

