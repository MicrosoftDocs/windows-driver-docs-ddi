---
UID: NF:wdm.RtlUnicodeStringToAnsiString
title: RtlUnicodeStringToAnsiString function
author: windows-driver-content
description: The RtlUnicodeStringToAnsiString routine converts a given Unicode string into an ANSI string.
old-location: kernel\rtlunicodestringtoansistring.htm
old-project: kernel
ms.assetid: d05b366c-0b09-4a82-8727-e5c39b82bf7f
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUnicodeStringToAnsiString, RtlUnicodeStringToAnsiString routine [Kernel-Mode Driver Architecture], k109_50e549a0-61fa-4a0f-b43f-de2f4c6dba31.xml, kernel.rtlunicodestringtoansistring, wdm/RtlUnicodeStringToAnsiString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlUnicodeStringToAnsiString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlUnicodeStringToAnsiString function


## -description


The <b>RtlUnicodeStringToAnsiString</b> routine converts a given Unicode string into an ANSI string.


## -parameters




### -param DestinationString [in, out]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure to hold the converted ANSI string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, and updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer. Otherwise, the routine uses the currently specified buffer to hold the string. 


### -param SourceString [in]

Pointer to the Unicode source string to be converted to ANSI.


### -param AllocateDestinationString [in]

<b>TRUE</b> if this routine is to allocate the buffer space for the <i>DestinationString</i>. If it does, the buffer must be deallocated by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff561899">RtlFreeAnsiString</a>.


## -returns



If the conversion succeeds, <b>RtlUnicodeStringToAnsiString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated, and no conversion was done.




## -remarks



The translation is done in accord with the current system-locale information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561729">RtlAnsiStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561899">RtlFreeAnsiString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

