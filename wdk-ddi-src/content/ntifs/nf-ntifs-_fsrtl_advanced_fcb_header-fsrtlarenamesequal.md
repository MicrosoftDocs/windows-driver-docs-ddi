---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAreNamesEqual
title: FsRtlAreNamesEqual function (ntifs.h)
description: The FsRtlAreNamesEqual routine determines whether two Unicode strings are equal.
old-location: ifsk\fsrtlarenamesequal.htm
tech.root: ifsk
ms.assetid: 4125e210-c3c2-475c-b516-617fca5d3d0e
ms.date: 04/16/2018
ms.keywords: FsRtlAreNamesEqual, FsRtlAreNamesEqual routine [Installable File System Drivers], fsrtlref_748ea4a2-40a9-47e7-8a7f-f67463082f81.xml, ifsk.fsrtlarenamesequal, ntifs/FsRtlAreNamesEqual
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlAreNamesEqual"
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
- FsRtlAreNamesEqual
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlAreNamesEqual function


## -description


The <b>FsRtlAreNamesEqual</b> routine determines whether two Unicode strings are equal. 


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

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlequalunicodestring">RtlEqualUnicodeString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

