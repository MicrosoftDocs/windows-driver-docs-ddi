---
UID: NF:ntifs.RtlUnicodeToOemN
title: RtlUnicodeToOemN function
author: windows-driver-content
description: The RtlUnicodeToOemN routine translates a given Unicode string to an OEM string, using the current system OEM code page.
old-location: ifsk\rtlunicodetooemn.htm
tech.root: ifsk
ms.assetid: bb9ec3d9-89cd-4c56-8020-f8f97c2ce69b
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlUnicodeToOemN, RtlUnicodeToOemN routine [Installable File System Drivers], ifsk.rtlunicodetooemn, ntifs/RtlUnicodeToOemN, rtlref_f78dd2e1-13f7-4622-ac13-9207c040b782.xml
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
-	RtlUnicodeToOemN
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUnicodeToOemN function


## -description


The <b>RtlUnicodeToOemN</b> routine translates a given Unicode string to an OEM string, using the current system OEM code page. 


## -parameters




### -param OemString [out]

Pointer to a caller-allocated buffer to receive the translated string. 


### -param MaxBytesInOemString [in]

Maximum number of bytes to be written to <i>OemString</i>. 


### -param BytesInOemString [out, optional]

Pointer to a caller-allocated variable that receives the number of bytes in the translated string. This parameter can be <b>NULL</b>. 


### -param UnicodeString [in]

Pointer to the Unicode source string to be translated. 


### -param BytesInUnicodeString [in]

Size, in bytes, of the string at <i>UnicodeString</i>. 


## -returns



<b>RtlUnicodeToOemN</b> returns STATUS_SUCCESS if the full string at <i>UnicodeString</i> was translated and returned at <i>OemString</i>. 




## -remarks



For the return value STATUS_BUFFER_OVERFLOW, the truncated string at <i>OemString</i> was translated without error. 

For the return value STATUS_SUCCESS, the value at <i>BytesInOemString</i>, if any, indicates the length of the returned string, rather than the given <i>MaxBytesInOemString</i>. 

<b>RtlUnicodeToOemN</b> does not modify the source string. It returns a null-terminated OEM string if the given <i>BytesInUnicodeString</i> included a NULL terminator and if the given <i>MaxBytesInOemString</i> did not cause truncation. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553157">RtlOemToUnicodeN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553251">RtlUnicodeStringToCountedOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553255">RtlUnicodeStringToOemString</a>
 

 

