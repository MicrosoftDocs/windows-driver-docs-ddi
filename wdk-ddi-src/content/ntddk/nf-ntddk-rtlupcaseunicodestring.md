---
UID: NF:ntddk.RtlUpcaseUnicodeString
title: RtlUpcaseUnicodeString function
author: windows-driver-content
description: The RtlUpcaseUnicodeString routine converts a copy of the source string to uppercase and writes the converted string in the destination buffer.
old-location: kernel\rtlupcaseunicodestring.htm
old-project: kernel
ms.assetid: fe3c6010-532b-4f3d-b3d3-a1c27d4a05f1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , R, RtlUpcaseUnicodeString, RtlUpcaseUnicodeString routine [Kernel-Mode Driver Architecture], S, U, a, c, d, e, g, i, k109_617db3d7-18d8-46eb-a555-59f99d9cae78.xml, kernel.rtlupcaseunicodestring, l, n, ntddk/RtlUpcaseUnicodeString, o, p, r, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlUpcaseUnicodeString
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlUpcaseUnicodeString function


## -description


The <b>RtlUpcaseUnicodeString</b> routine converts a copy of the source string to uppercase and writes the converted string in the destination buffer.


## -syntax


````
NTSTATUS RtlUpcaseUnicodeString(
  _Inout_ PUNICODE_STRING  DestinationString,
  _In_    PCUNICODE_STRING SourceString,
  _In_    BOOLEAN          AllocateDestinationString
);
````


## -parameters




### -param DestinationString [in, out]

Pointer to a caller-allocated buffer for the converted Unicode string.


### -param SourceString [in]

Pointer to the source Unicode string to be converted to uppercase.


### -param AllocateDestinationString [in]

Specifies if <b>RtlUpcaseUnicodeString</b> is to allocate the buffer space for the <i>DestinationString</i>. If it does, the buffer must be deallocated by calling <b>RtlFreeUnicodeString</b>.


## -returns



If the operation succeeds, <b>RtlUpcaseUnicodeString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated, and no conversion was done.




## -see-also

<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>



<a href="..\wdm\nf-wdm-rtlupcaseunicodechar.md">RtlUpcaseUnicodeChar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUpcaseUnicodeString routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

