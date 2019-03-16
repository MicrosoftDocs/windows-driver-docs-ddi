---
UID: NF:ntifs.RtlDowncaseUnicodeString
title: RtlDowncaseUnicodeString function (ntifs.h)
description: The RtlDowncaseUnicodeString routine converts the specified Unicode source string to lowercase. The translation conforms to the current system locale information.
old-location: ifsk\rtldowncaseunicodestring.htm
tech.root: ifsk
ms.assetid: c611b051-45fe-4509-bf2c-7059d578ea05
ms.date: 04/16/2018
ms.keywords: RtlDowncaseUnicodeString, RtlDowncaseUnicodeString routine [Installable File System Drivers], ifsk.rtldowncaseunicodestring, ntifs/RtlDowncaseUnicodeString, rtlref_140e7faa-096a-49df-a2b7-87776cfc5b38.xml
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlDowncaseUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlDowncaseUnicodeString function


## -description


The <b>RtlDowncaseUnicodeString</b> routine converts the specified Unicode source string to lowercase. The translation conforms to the current system locale information.


## -parameters




### -param DestinationString

Pointer to a caller-allocated buffer to receive the converted Unicode string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the Unicode data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlDowncaseUnicodeString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the source Unicode string to be converted to lowercase. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlDowncaseUnicodeString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeUnicodeString</b>. 


## -returns



If the operation succeeds, <b>RtlDowncaseUnicodeString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated and no conversion was done. 




## -remarks



If caller sets <i>AllocateDestinationString</i> to <b>TRUE</b>, <b>RtlDowncaseUnicodeString</b> replaces the <b>Buffer</b> member of <i>DestinationString</i> with a pointer to the buffer it allocates. The old value can be overwritten even when the routine returns an error status code.

<b>RtlDowncaseUnicodeString</b> does not modify the source string.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561903">RtlFreeUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563005">RtlUpcaseUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

