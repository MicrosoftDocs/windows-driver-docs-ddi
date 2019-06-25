---
UID: NF:wdm.RtlInitUnicodeString
title: RtlInitUnicodeString function (wdm.h)
description: For more information, see the WdmlibRtlInitUnicodeStringEx function.
old-location: kernel\rtlinitunicodestring.htm
tech.root: kernel
ms.assetid: c6ef7438-36a6-4da6-b745-2985d9b30614
ms.date: 04/30/2018
ms.keywords: RtlInitUnicodeString, RtlInitUnicodeString routine [Kernel-Mode Driver Architecture], k109_10e59fa9-6f57-45db-bc11-520660f43b13.xml, kernel.rtlinitunicodestring, wdm/RtlInitUnicodeString
ms.topic: function
req.header: wdm.h
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlInitUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInitUnicodeString function


## -description


For more information, see  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdmsec/nf-wdmsec-wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a> function.


## -parameters




### -param DestinationString [out]

For more information, see  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdmsec/nf-wdmsec-wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a> function.


### -param SourceString [in, optional]

For more information, see  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdmsec/nf-wdmsec-wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a> function.


## -returns



For more information, see  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdmsec/nf-wdmsec-wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a> function.




## -remarks



The <b>RTL_CONSTANT_STRING</b> macro creates a string or Unicode string structure to hold a counted string.


<pre class="syntax">STRING RTL_CONSTANT_STRING(
  [in]  PCSZ SourceString
);

UNICODE_STRING RTL_CONSTANT_STRING(
  [in]  PCWSTR SourceString
);</pre>




<b>RTL_CONSTANT_STRING</b> returns either a string structure or Unicode string structure.

The <b>RTL_CONSTANT_STRING</b> macro replaces the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlinitansistring">RtlInitAnsiString</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlinitstring">RtlInitString</a>, and <b>RtlInitUnicodeString</b> routines when passing a constant string.

You can use <b>RTL_CONSTANT_STRING</b> to initialize global variables.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringinit">RtlUnicodeStringInit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntstrsafe/nf-ntstrsafe-rtlunicodestringinitex">RtlUnicodeStringInitEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdmsec/nf-wdmsec-wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a>
 

 

