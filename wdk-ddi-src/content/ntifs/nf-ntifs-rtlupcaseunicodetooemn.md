---
UID: NF:ntifs.RtlUpcaseUnicodeToOemN
title: RtlUpcaseUnicodeToOemN function
author: windows-driver-content
description: The RtlUpcaseUnicodeToOemN routine translates a given Unicode string into an uppercase OEM string, using the current system OEM code page.
old-location: ifsk\rtlupcaseunicodetooemn.htm
old-project: ifsk
ms.assetid: d4d802c1-66e9-4342-ba7d-d9e5a464362e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlUpcaseUnicodeToOemN, RtlUpcaseUnicodeToOemN routine [Installable File System Drivers], ifsk.rtlupcaseunicodetooemn, ntifs/RtlUpcaseUnicodeToOemN, rtlref_b1fcf08b-c13f-4b60-a570-f4bffe730ba4.xml
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
-	RtlUpcaseUnicodeToOemN
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlUpcaseUnicodeToOemN function


## -description


The <b>RtlUpcaseUnicodeToOemN</b> routine translates a given Unicode string into an uppercase OEM string, using the current system OEM code page. 


## -syntax


````
NTSTATUS RtlUpcaseUnicodeToOemN(
  _Out_     PCHAR  OemString,
  _In_      ULONG  MaxBytesInOemString,
  _Out_opt_ PULONG BytesInOemString,
  _In_      PCWCH  UnicodeString,
  _In_      ULONG  BytesInUnicodeString
);
````


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



<b>RtlUnicodeToOemN</b> returns STATUS_SUCCESS if the full string at <i>UnicodeString</i> was successfully translated, converted to uppercase, and returned at <i>OemString</i>. Otherwise, it can return STATUS_BUFFER_OVERFLOW if the destination string must be truncated to fit the given <i>MaxBytesInOemString</i>. 




## -remarks



For the return value STATUS_BUFFER_OVERFLOW, the truncated string at <i>OemString</i> was translated without error. 

For the return value STATUS_SUCCESS, the value at <i>BytesInOemString</i>, if any, indicates the length of the returned string, rather than the given <i>MaxBytesInOemString</i>. 

This routine does not modify the source string. It returns a null-terminated OEM string if the given <i>BytesInUnicodeString</i> included a NULL terminator and if the given <i>MaxBytesInOemString</i> did not cause truncation.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtooemstring.md">RtlUpcaseUnicodeStringToOemString</a>



<a href="..\ntifs\nf-ntifs-rtlunicodetooemn.md">RtlUnicodeToOemN</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtocountedoemstring.md">RtlUpcaseUnicodeStringToCountedOemString</a>



<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemsize.md">RtlUnicodeStringToOemSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUpcaseUnicodeToOemN routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

