---
UID: NF:ntifs.RtlUpcaseUnicodeToMultiByteN
title: RtlUpcaseUnicodeToMultiByteN function
author: windows-driver-content
description: The RtlUpcaseUnicodeToMultiByteN routine translates the specified Unicode string into a new uppercase character string, using the current system ANSI code page (ACP). The translated string is not necessarily from a multibyte character set.
old-location: ifsk\rtlupcaseunicodetomultibyten.htm
old-project: ifsk
ms.assetid: a79a5d3b-ed1c-42fa-b491-0ad0b3dfc921
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rtlupcaseunicodetomultibyten, RtlUpcaseUnicodeToMultiByteN, rtlref_a6ac52da-a3c7-4c16-8b8c-3086868fe4e2.xml, RtlUpcaseUnicodeToMultiByteN routine [Installable File System Drivers], ntifs/RtlUpcaseUnicodeToMultiByteN
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlUpcaseUnicodeToMultiByteN
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlUpcaseUnicodeToMultiByteN function


## -description


The <b>RtlUpcaseUnicodeToMultiByteN</b> routine translates the specified Unicode string into a new uppercase character string, using the current system ANSI code page (ACP). The translated string is not necessarily from a multibyte character set. 


## -syntax


````
NTSTATUS RtlUpcaseUnicodeToMultiByteN(
  _Out_     PCHAR  MultiByteString,
  _In_      ULONG  MaxBytesInMultiByteString,
  _Out_opt_ PULONG BytesInMultiByteString,
  _In_      PCWCH  UnicodeString,
  _In_      ULONG  BytesInUnicodeString
);
````


## -parameters




#### - MultiByteString [out]

Pointer to a caller-allocated buffer to receive the translated string. 


#### - MaxBytesInMultiByteString [in]

Maximum number of bytes to be written at <i>MultiByteString</i>. If this value causes the translated string to be truncated, <b>RtlUpcaseUnicodeToMultiByteN</b> does not return an error status. 


#### - BytesInMultiByteString [out, optional]

Pointer to a caller-allocated variable that receives the length, in bytes, of the translated string. This parameter can be <b>NULL</b>. 


#### - UnicodeString [in]

Pointer to the Unicode source string to be translated. 


#### - BytesInUnicodeString [in]

Size, in bytes, of the string at <i>UnicodeString</i>. 


## -returns


<b>RtlUpcaseUnicodeToMultiByteN</b> returns STATUS_SUCCESS. 



## -remarks


<b>RtlUpcaseUnicodeToMultiByteN</b> translates the given Unicode string using the current system ANSI code page installed at system boot time and converts the translated string to uppercase. 

This routine does not modify the source string. It returns a NULL-terminated ANSI string if the given <i>BytesInUnicodeString</i> included a NULL terminator and if the given <i>MaxBytesInMultiByteString</i> did not cause truncation.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 



## -see-also

<a href="..\ntifs\nf-ntifs-rtlmultibytetounicoden.md">RtlMultiByteToUnicodeN</a>

<a href="..\ntifs\nf-ntifs-rtlunicodetomultibytesize.md">RtlUnicodeToMultiByteSize</a>

<a href="..\ntifs\nf-ntifs-rtlunicodetomultibyten.md">RtlUnicodeToMultiByteN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUpcaseUnicodeToMultiByteN routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

