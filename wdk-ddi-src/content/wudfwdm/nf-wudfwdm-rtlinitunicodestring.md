---
UID: NF:wudfwdm.RtlInitUnicodeString
title: RtlInitUnicodeString function
author: windows-driver-content
description: For more information, see the WdmlibRtlInitUnicodeStringEx function.
old-location: kernel\rtlinitunicodestring.htm
old-project: kernel
ms.assetid: c6ef7438-36a6-4da6-b745-2985d9b30614
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
product:
- Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---

# RtlInitUnicodeString function


## -description


For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a> function.


## -syntax


````
VOID RtlInitUnicodeString(
  _Out_    PUNICODE_STRING DestinationString,
  _In_opt_ PCWSTR          SourceString
);
````


## -parameters




### -param DestinationString [out]

For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a> function.


### -param SourceString [in, optional]

For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a> function.


## -returns



For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a> function.




## -remarks



The <b>RTL_CONSTANT_STRING</b> macro creates a string or Unicode string structure to hold a counted string.


<pre class="syntax">STRING RTL_CONSTANT_STRING(
  [in]  PCSZ SourceString
);

UNICODE_STRING RTL_CONSTANT_STRING(
  [in]  PCWSTR SourceString
);</pre>




<b>RTL_CONSTANT_STRING</b> returns either a string structure or Unicode string structure.

The <b>RTL_CONSTANT_STRING</b> macro replaces the <a href="..\wdm\nf-wdm-rtlinitansistring.md">RtlInitAnsiString</a>, <a href="..\wdm\nf-wdm-rtlinitstring.md">RtlInitString</a>, and <b>RtlInitUnicodeString</b> routines when passing a constant string.

You can use <b>RTL_CONSTANT_STRING</b> to initialize global variables.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdmsec\nf-wdmsec-wdmlibrtlinitunicodestringex.md">WdmlibRtlInitUnicodeStringEx</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinitex.md">RtlUnicodeStringInitEx</a>



<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinit.md">RtlUnicodeStringInit</a>



 

 



