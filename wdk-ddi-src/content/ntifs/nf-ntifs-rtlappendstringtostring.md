---
UID: NF:ntifs.RtlAppendStringToString
title: RtlAppendStringToString function (ntifs.h)
description: The RtlAppendStringToString routine concatenates two counted strings. It copies bytes from the source up to the length of the destination buffer.
old-location: ifsk\rtlappendstringtostring.htm
tech.root: ifsk
ms.assetid: 8cd94502-c11a-4e6a-87f6-0c6034b6ac09
ms.date: 04/16/2018
keywords: ["RtlAppendStringToString function"]
ms.keywords: RtlAppendStringToString, RtlAppendStringToString routine [Installable File System Drivers], ifsk.rtlappendstringtostring, ntifs/RtlAppendStringToString, rtlref_a5cf2f54-1094-44ea-8b05-0c3d08aa5abc.xml
f1_keywords:
 - "ntifs/RtlAppendStringToString"
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000, and later versions of all Windows operating systems.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlAppendStringToString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlAppendStringToString function


## -description


The <b>RtlAppendStringToString</b> routine concatenates two counted strings. It copies bytes from the source up to the length of the destination buffer.


## -parameters




### -param Destination [in, out]

A pointer to a counted string to which the string at <i>Source</i> should be appended. 


### -param Source [in]

A pointer to a counted string to be appended to the string at <i>Destination</i>. 


## -returns



The <b>RtlAppendStringToString</b> routine returns STATUS_SUCCESS if it appended the string at <i>Source</i> to the string at <i>Destination</i>. <b>RtlAppendStringToString</b> returns STATUS_BUFFER_TOO_SMALL if the <b>MaximumLength</b> of the <i>Destination</i> string is too small to allow the source string to be appended. 




## -remarks



The sum of the <b>Length</b> members of the <i>Destination</i> and <i>Source</i> strings must be less than or equal to the <b>MaximumLength</b> of the <i>Destination</i> string.

For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlappendunicodestringtostring">RtlAppendUnicodeStringToString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlappendunicodetostring">RtlAppendUnicodeToString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitstring">RtlInitString</a>
 

 

