---
UID: NF:wdm.RtlInitAnsiString
title: RtlInitAnsiString function
author: windows-driver-content
description: The RtlInitAnsiString routine initializes a counted string of ANSI characters.
old-location: kernel\rtlinitansistring.htm
old-project: kernel
ms.assetid: 7b535ea0-091f-4a1b-bfb7-db3cfabbe846
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlInitAnsiString
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
req.alt-api: RtlInitAnsiString
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (See Remarks section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlInitAnsiString function



## -description
The <b>RtlInitAnsiString</b> routine initializes a counted string of ANSI characters.



## -syntax

````
VOID RtlInitAnsiString(
  _Out_    PANSI_STRING DestinationString,
  _In_opt_ PCSZ         SourceString
);
````


## -parameters

### -param DestinationString [out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure to be initialized.


### -param SourceString [in, optional]

A pointer to a null-terminated character string. This string is used to initialize the counted string pointed to by <i>DestinationString</i>.


## -returns
None


## -remarks
This routine initializes a counted character string.

The routine copies the <i>SourceString</i> pointer value to the <b>Buffer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure pointed to by <i>DestinationString</i>. The <b>Length</b> member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The <b>MaximumLength</b> member of the structure is set to the length, in bytes, of the source string, including the terminating null. If <i>SourceString</i> is <b>NULL</b>, <b>Length</b> and <b>MaximumLength</b> are both set to zero.

<b>RtlInitAnsiString</b> does not alter the source string pointed to by <i>SourceString</i>.

Callers of <b>RtlInitAnsiString</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the <i>DestinationString</i> buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other <b>Rtl<i>Xxx</i>String</b> routines cannot be called at IRQL &gt; PASSIVE_LEVEL.

The <b>RTL_CONSTANT_STRING</b> macro creates a string or Unicode string structure to hold a counted string.


<pre class="syntax">STRING RTL_CONSTANT_STRING(
  [in]  PCSZ SourceString
);

UNICODE_STRING RTL_CONSTANT_STRING(
  [in]  PCWSTR SourceString
);</pre>




Pointer to a null-terminated string to initialize the counted string with.

<b>RTL_CONSTANT_STRING</b> returns either a string structure or Unicode string structure.

The <b>RTL_CONSTANT_STRING</b> macro replaces the <b>RtlInitAnsiString</b>, <a href="..\wdm\nf-wdm-rtlinitstring.md">RtlInitString</a>, and <a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a> routines when passing a constant string.

You can use <b>RTL_CONSTANT_STRING</b> to initialize global variables.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlInitAnsiString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

