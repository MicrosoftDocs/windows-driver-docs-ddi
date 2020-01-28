---
UID: NF:ntifs.RtlFreeOemString
title: RtlFreeOemString function (ntifs.h)
description: The RtlFreeOemString routine releases storage that was allocated by any of the Rtl..ToOemString routines.
old-location: ifsk\rtlfreeoemstring.htm
tech.root: ifsk
ms.assetid: cd9bc03d-1f57-420c-9430-d2d742f654e1
ms.date: 04/16/2018
ms.keywords: RtlFreeOemString, RtlFreeOemString routine [Installable File System Drivers], ifsk.rtlfreeoemstring, ntifs/RtlFreeOemString, rtlref_ffc98e3c-a96f-4250-a527-bcd1ba2ce506.xml
f1_keywords:
 - "ntifs/RtlFreeOemString"
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlFreeOemString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFreeOemString function


## -description


The <b>RtlFreeOemString</b> routine releases storage that was allocated by any of the <b>Rtl..ToOemString</b> routines. 


## -parameters




### -param OemString [in, out]

Pointer to the OEM string buffer that was allocated by a preceding call to <b>RtlUnicodeStringToCountedOemString</b>, <b>RtlUnicodeStringToOemString</b>, <b>RtlUpcaseUnicodeStringToCountedOemString</b>, or <b>RtlUpcaseUnicodeStringToOemString</b>. 


## -returns



None




## -remarks



<b>RtlFreeOemString</b> deallocates memory only for the buffered OEM string. This routine does not free the buffered Unicode string passed in a preceding call to the <b>Rtl..ToOemString</b> routine. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff558741(v=vs.85)">OEM_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodestringtocountedoemstring">RtlUnicodeStringToCountedOemString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodestringtooemstring">RtlUnicodeStringToOemString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlupcaseunicodestringtocountedoemstring">RtlUpcaseUnicodeStringToCountedOemString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlupcaseunicodestringtooemstring">RtlUpcaseUnicodeStringToOemString</a>
 

 

