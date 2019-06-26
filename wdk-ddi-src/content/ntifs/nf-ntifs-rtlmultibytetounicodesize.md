---
UID: NF:ntifs.RtlMultiByteToUnicodeSize
title: RtlMultiByteToUnicodeSize function (ntifs.h)
description: The RtlMultiByteToUnicodeSize routine determines the number of bytes that are required to store the Unicode translation for the specified source string.
old-location: ifsk\rtlmultibytetounicodesize.htm
tech.root: ifsk
ms.assetid: f285e319-23ef-4951-8fb3-107cd54a23b3
ms.date: 04/16/2018
ms.keywords: RtlMultiByteToUnicodeSize, RtlMultiByteToUnicodeSize routine [Installable File System Drivers], ifsk.rtlmultibytetounicodesize, ntifs/RtlMultiByteToUnicodeSize, rtlref_f2e77505-7c59-4bb2-993f-622ea16a83c6.xml
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
- RtlMultiByteToUnicodeSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlMultiByteToUnicodeSize function


## -description


The <b>RtlMultiByteToUnicodeSize</b> routine determines the number of bytes that are required to store the Unicode translation for the specified source string. The translation is assumed to use the current system ANSI code page (ACP). The source string is not necessarily from a multibyte character set. 


## -parameters




### -param BytesInUnicodeString [out]

Pointer to a caller-allocated variable that receives the number of bytes that are required to store the translated string. 


### -param MultiByteString [in]

Pointer to the source string for which the Unicode length is to be calculated. 


### -param BytesInMultiByteString [in]

Length, in bytes, of the source string. 


## -returns



<b>RtlMultiByteToUnicodeSize</b> returns STATUS_SUCCESS. 




## -remarks



<b>RtlMultiByteToUnicodeSize</b> can be called to determine how much memory to allocate, or possibly, the value to specify for <i>MaxBytesInUnicodeString</i>, before translating a multibyte string into Unicode with <b>RtlMultiByteToUnicodeN</b>. The returned value does not include space for a NULL terminator for the Unicode string. 

Like <b>RtlMultiByteToUnicodeN</b>, <b>RtlMultiByteToUnicodeSize</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlmultibytetounicoden">RtlMultiByteToUnicodeN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlunicodetomultibytesize">RtlUnicodeToMultiByteSize</a>
 

 

