---
UID: NF:ntddk.RtlUpcaseUnicodeString
title: RtlUpcaseUnicodeString function
author: windows-driver-content
description: The RtlUpcaseUnicodeString routine converts a copy of the source string to uppercase and writes the converted string in the destination buffer.
old-location: kernel\rtlupcaseunicodestring.htm
tech.root: kernel
ms.assetid: fe3c6010-532b-4f3d-b3d3-a1c27d4a05f1
ms.date: 4/30/2018
ms.keywords: RtlUpcaseUnicodeString, RtlUpcaseUnicodeString routine [Kernel-Mode Driver Architecture], k109_617db3d7-18d8-46eb-a555-59f99d9cae78.xml, kernel.rtlupcaseunicodestring, ntddk/RtlUpcaseUnicodeString
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlUpcaseUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUpcaseUnicodeString function


## -description


The <b>RtlUpcaseUnicodeString</b> routine converts a copy of the source string to uppercase and writes the converted string in the destination buffer.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561903">RtlFreeUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563003">RtlUpcaseUnicodeChar</a>
 

 

