---
UID: NF:ntifs.RtlUnicodeStringToOemSize
title: RtlUnicodeStringToOemSize macro (ntifs.h)
description: The RtlUnicodeStringToOemSize routine determines the size, in bytes, that a given Unicode string will be after it is translated into an OEM string.
old-location: ifsk\rtlunicodestringtooemsize.htm
tech.root: ifsk
ms.assetid: 0e648c99-6d1a-4515-af17-a16e88351f45
ms.date: 04/16/2018
ms.keywords: RtlUnicodeStringToOemSize, RtlUnicodeStringToOemSize routine [Installable File System Drivers], ifsk.rtlunicodestringtooemsize, ntifs/RtlUnicodeStringToOemSize, rtlref_836e23f0-2e1a-474e-a66c-615f260e2f4f.xml
ms.topic: macro
f1_keywords:
 - "ntifs/RtlUnicodeStringToOemSize"
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
- RtlUnicodeStringToOemSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeStringToOemSize macro


## -description


The <b>RtlUnicodeStringToOemSize</b> routine determines the size, in bytes, that a given Unicode string will be after it is translated into an OEM string. 


## -parameters




### -param STRING

<p>Pointer to a caller-allocated Unicode string. </p>






## -remarks



<b>RtlUnicodeStringToOemSize</b> can be called to determine how much memory to allocate when translating a Unicode string to OEM characters with <b>RtlUnicodeStringToOemString</b> or <b>RtlUpcaseUnicodeStringToOemString</b>. The returned value includes space for a NULL terminator for the OEM string. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtounicodesize">RtlOemStringToUnicodeSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodestringtooemstring">RtlUnicodeStringToOemString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlupcaseunicodestringtooemstring">RtlUpcaseUnicodeStringToOemString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

