---
UID: NF:ntifs.RtlUpcaseUnicodeToMultiByteN
title: RtlUpcaseUnicodeToMultiByteN function
author: windows-driver-content
description: The RtlUpcaseUnicodeToMultiByteN routine translates the specified Unicode string into a new uppercase character string, using the current system ANSI code page (ACP). The translated string is not necessarily from a multibyte character set.
old-location: ifsk\rtlupcaseunicodetomultibyten.htm
tech.root: ifsk
ms.assetid: a79a5d3b-ed1c-42fa-b491-0ad0b3dfc921
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlUpcaseUnicodeToMultiByteN, RtlUpcaseUnicodeToMultiByteN routine [Installable File System Drivers], ifsk.rtlupcaseunicodetomultibyten, ntifs/RtlUpcaseUnicodeToMultiByteN, rtlref_a6ac52da-a3c7-4c16-8b8c-3086868fe4e2.xml
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlUpcaseUnicodeToMultiByteN
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUpcaseUnicodeToMultiByteN function


## -description


The <b>RtlUpcaseUnicodeToMultiByteN</b> routine translates the specified Unicode string into a new uppercase character string, using the current system ANSI code page (ACP). The translated string is not necessarily from a multibyte character set. 


## -parameters




### -param MultiByteString [out]

Pointer to a caller-allocated buffer to receive the translated string. 


### -param MaxBytesInMultiByteString [in]

Maximum number of bytes to be written at <i>MultiByteString</i>. If this value causes the translated string to be truncated, <b>RtlUpcaseUnicodeToMultiByteN</b> does not return an error status. 


### -param BytesInMultiByteString [out, optional]

Pointer to a caller-allocated variable that receives the length, in bytes, of the translated string. This parameter can be <b>NULL</b>. 


### -param UnicodeString [in]

Pointer to the Unicode source string to be translated. 


### -param BytesInUnicodeString [in]

Size, in bytes, of the string at <i>UnicodeString</i>. 


## -returns



<b>RtlUpcaseUnicodeToMultiByteN</b> returns STATUS_SUCCESS. 




## -remarks



<b>RtlUpcaseUnicodeToMultiByteN</b> translates the given Unicode string using the current system ANSI code page installed at system boot time and converts the translated string to uppercase. 

This routine does not modify the source string. It returns a NULL-terminated ANSI string if the given <i>BytesInUnicodeString</i> included a NULL terminator and if the given <i>MaxBytesInMultiByteString</i> did not cause truncation.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553113">RtlMultiByteToUnicodeN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553261">RtlUnicodeToMultiByteN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553266">RtlUnicodeToMultiByteSize</a>
 

 

