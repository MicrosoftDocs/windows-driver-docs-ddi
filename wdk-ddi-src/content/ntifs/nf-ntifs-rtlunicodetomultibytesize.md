---
UID: NF:ntifs.RtlUnicodeToMultiByteSize
title: RtlUnicodeToMultiByteSize function
author: windows-driver-content
description: The RtlUnicodeToMultiByteSize routine determines the number of bytes that are required to store the multibyte translation for the specified Unicode string. The translation is assumed to use the current system ANSI code page (ACP).
old-location: ifsk\rtlunicodetomultibytesize.htm
old-project: ifsk
ms.assetid: 603a5554-2e61-49f1-a4b1-e0f0f3ba36c8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlUnicodeToMultiByteSize, rtlref_f0366c3a-b185-45f3-a7e2-541168b842d3.xml, ifsk.rtlunicodetomultibytesize, ntifs/RtlUnicodeToMultiByteSize, RtlUnicodeToMultiByteSize routine [Installable File System Drivers]
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
-	RtlUnicodeToMultiByteSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlUnicodeToMultiByteSize function


## -description


The <b>RtlUnicodeToMultiByteSize</b> routine determines the number of bytes that are required to store the multibyte translation for the specified Unicode string. The translation is assumed to use the current system ANSI code page (ACP). 


## -syntax


````
NTSTATUS RtlUnicodeToMultiByteSize(
  _Out_ PULONG BytesInMultiByteString,
  _In_  PCWCH  UnicodeString,
  _In_  ULONG  BytesInUnicodeString
);
````


## -parameters




### -param BytesInMultiByteString [out]

Pointer to a caller-allocated variable that receives the number of bytes required to store the translated string. 


### -param UnicodeString [in]

Pointer to the Unicode string for which the multibyte length is to be calculated. 


### -param BytesInUnicodeString [in]

Length, in bytes, of the source string. 


## -returns



<b>RtlUnicodeToMultiByteSize</b> returns STATUS_SUCCESS. 




## -remarks



<b>RtlUnicodeToMultiByteSize</b> can be called to determine how much memory to allocate, or possibly the value to specify for <i>MaxBytesInMultiByteString</i>, before translating a Unicode string to ANSI with <b>RtlUnicodeToMultiByteN</b> or <b>RtlUpcaseUnicodeToMultiByteN</b>. The returned value does not include space for a NULL terminator for the ANSI string. 

Like <b>RtlUnicodeToMultiByteN</b>, <b>RtlUnicodeToMultiByteSize</b> supports only precomposed Unicode characters that are mapped to the current system ANSI code page installed at system boot. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlupcaseunicodetomultibyten.md">RtlUpcaseUnicodeToMultiByteN</a>



<a href="..\ntifs\nf-ntifs-rtlunicodetomultibyten.md">RtlUnicodeToMultiByteN</a>



<a href="..\ntifs\nf-ntifs-rtlmultibytetounicodesize.md">RtlMultiByteToUnicodeSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUnicodeToMultiByteSize routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

