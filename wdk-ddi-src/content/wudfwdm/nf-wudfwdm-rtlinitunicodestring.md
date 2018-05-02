---
UID: NF:wudfwdm.RtlInitUnicodeString
title: RtlInitUnicodeString function
author: windows-driver-content
description: For more information, see the WdmlibRtlInitUnicodeStringEx function.
old-location: kernel\rtlinitunicodestring.htm
old-project: kernel
ms.assetid: c6ef7438-36a6-4da6-b745-2985d9b30614
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlInitUnicodeString, RtlInitUnicodeString routine [Kernel-Mode Driver Architecture], k109_10e59fa9-6f57-45db-bc11-520660f43b13.xml, kernel.rtlinitunicodestring, wdm/RtlInitUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
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
req.irql: For more information, see  the Remarks section of the WdmlibRtlInitUnicodeStringEx  function.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlInitUnicodeString
product: Windows
targetos: Windows
req.typenames: 
---

# RtlInitUnicodeString function


## -description


For more information, see  the <a href="https://msdn.microsoft.com/79DEDC5B-2A9B-4493-9CB3-7290BEBBD291">WdmlibRtlInitUnicodeStringEx</a> function.


## -parameters




### -param DestinationString [out]

For more information, see  the <a href="https://msdn.microsoft.com/79DEDC5B-2A9B-4493-9CB3-7290BEBBD291">WdmlibRtlInitUnicodeStringEx</a> function.


### -param SourceString [in, optional]

For more information, see  the <a href="https://msdn.microsoft.com/79DEDC5B-2A9B-4493-9CB3-7290BEBBD291">WdmlibRtlInitUnicodeStringEx</a> function.


## -returns



For more information, see  the <a href="https://msdn.microsoft.com/79DEDC5B-2A9B-4493-9CB3-7290BEBBD291">WdmlibRtlInitUnicodeStringEx</a> function.




## -remarks



The <b>RTL_CONSTANT_STRING</b> macro creates a string or Unicode string structure to hold a counted string.


<pre class="syntax">STRING RTL_CONSTANT_STRING(
  [in]  PCSZ SourceString
);

UNICODE_STRING RTL_CONSTANT_STRING(
  [in]  PCWSTR SourceString
);</pre>




<b>RTL_CONSTANT_STRING</b> returns either a string structure or Unicode string structure.

The <b>RTL_CONSTANT_STRING</b> macro replaces the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561918">RtlInitAnsiString</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff561929">RtlInitString</a>, and <b>RtlInitUnicodeString</b> routines when passing a constant string.

You can use <b>RTL_CONSTANT_STRING</b> to initialize global variables.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562954">RtlUnicodeStringInit</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562958">RtlUnicodeStringInitEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/79DEDC5B-2A9B-4493-9CB3-7290BEBBD291">WdmlibRtlInitUnicodeStringEx</a>
 

 

