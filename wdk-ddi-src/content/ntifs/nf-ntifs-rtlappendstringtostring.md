---
UID: NF:ntifs.RtlAppendStringToString
title: RtlAppendStringToString function
author: windows-driver-content
description: The RtlAppendStringToString routine concatenates two counted strings. It copies bytes from the source up to the length of the destination buffer.
old-location: ifsk\rtlappendstringtostring.htm
old-project: ifsk
ms.assetid: 8cd94502-c11a-4e6a-87f6-0c6034b6ac09
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlAppendStringToString, RtlAppendStringToString routine [Installable File System Drivers], ifsk.rtlappendstringtostring, ntifs/RtlAppendStringToString, rtlref_a5cf2f54-1094-44ea-8b05-0c3d08aa5abc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlAppendStringToString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlAppendStringToString function


## -description


The <b>RtlAppendStringToString</b> routine concatenates two counted strings. It copies bytes from the source up to the length of the destination buffer.


## -syntax


````
NTSTATUS RtlAppendStringToString(
  _Inout_       PSTRING Destination,
  _In_    const STRING  *Source
);
````


## -parameters




### -param Destination [in, out]

A pointer to a counted string to which the string at <i>Source</i> should be appended. 


### -param Source [in]

A pointer to a counted string to be appended to the string at <i>Destination</i>. 


## -returns



The <b>RtlAppendStringToString</b> routine returns STATUS_SUCCESS if it appended the string at <i>Source</i> to the string at <i>Destination</i>. <b>RtlAppendStringToString</b> returns STATUS_BUFFER_TOO_SMALL if the <b>MaximumLength</b> of the <i>Destination</i> string is too small to allow the source string to be appended. 




## -remarks



The sum of the <b>Length</b> members of the <i>Destination</i> and <i>Source</i> strings must be less than or equal to the <b>MaximumLength</b> of the <i>Destination</i> string.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\wdm\nf-wdm-rtlappendunicodestringtostring.md">RtlAppendUnicodeStringToString</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlappendunicodetostring.md">RtlAppendUnicodeToString</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlappendunicodestringtostring.md">RtlAppendUnicodeStringToString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlAppendStringToString routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

