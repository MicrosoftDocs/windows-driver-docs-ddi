---
UID: NF:ntifs.RtlOemStringToUnicodeSize
title: RtlOemStringToUnicodeSize macro (ntifs.h)
description: The RtlOemStringToUnicodeSize routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string.
old-location: ifsk\rtloemstringtounicodesize.htm
tech.root: ifsk
ms.assetid: e54d0e3f-4e46-43b5-8338-b6e2f2a14c56
ms.date: 04/16/2018
keywords: ["RtlOemStringToUnicodeSize macro"]
ms.keywords: RtlOemStringToUnicodeSize, RtlOemStringToUnicodeSize routine [Installable File System Drivers], ifsk.rtloemstringtounicodesize, ntifs/RtlOemStringToUnicodeSize, rtlref_5f048569-d84e-43ee-8d51-1281f18c7ddf.xml
f1_keywords:
 - "ntifs/RtlOemStringToUnicodeSize"
 - "RtlOemStringToUnicodeSize"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
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
- RtlOemStringToUnicodeSize
targetos: Windows
req.typenames: 
---

# RtlOemStringToUnicodeSize macro


## -description


The <b>RtlOemStringToUnicodeSize</b> routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string. 


## -parameters




### -param STRING

<p>Pointer to a caller-allocated OEM string. </p>






## -remarks



<b>RtlOemStringToUnicodeSize</b> can be called to determine how much memory to allocate when translating an OEM string to Unicode with <b>RtlOemStringToUnicodeString</b>. The returned value includes space for the NULL terminator. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff558741(v=vs.85)">OEM_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtocountedunicodesize">RtlOemStringToCountedUnicodeSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtounicodestring">RtlOemStringToUnicodeString</a>
 

 

