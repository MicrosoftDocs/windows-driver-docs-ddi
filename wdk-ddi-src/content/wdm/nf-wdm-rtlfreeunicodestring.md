---
UID: NF:wdm.RtlFreeUnicodeString
title: RtlFreeUnicodeString function (wdm.h)
description: The RtlFreeUnicodeString routine releases storage that was allocated by RtlAnsiStringToUnicodeString or RtlUpcaseUnicodeString.
old-location: kernel\rtlfreeunicodestring.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlFreeUnicodeString function"]
ms.keywords: RtlFreeUnicodeString, RtlFreeUnicodeString routine [Kernel-Mode Driver Architecture], k109_c23e6c5e-d2dd-4b88-8249-5f88ad8482ad.xml, kernel.rtlfreeunicodestring, wdm/RtlFreeUnicodeString
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFreeUnicodeString
 - wdm/RtlFreeUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlFreeUnicodeString
---

# RtlFreeUnicodeString function


## -description

The <b>RtlFreeUnicodeString</b> routine releases storage that was allocated by <b>RtlAnsiStringToUnicodeString</b> or <b>RtlUpcaseUnicodeString</b>.

## -parameters

### -param UnicodeString 

[in, out]
Pointer to the Unicode string buffer previously allocated by <b>RtlAnsiStringToUnicodeString</b> or <b>RtlUpcaseUnicodeString</b>.

## -returns

None

## -remarks

This routine does not release the ANSI string buffer passed to <b>RtlAnsiStringToUnicodeString</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodestring">RtlAnsiStringToUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlupcaseunicodestring">RtlUpcaseUnicodeString</a>
