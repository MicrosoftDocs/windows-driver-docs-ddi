---
UID: NF:wdm.RtlEqualUnicodeString
title: RtlEqualUnicodeString function (wdm.h)
description: The RtlEqualUnicodeString routine compares two Unicode strings to determine whether they are equal.
old-location: kernel\rtlequalunicodestring.htm
tech.root: kernel
ms.assetid: ba50fcac-acb1-43de-aacc-b47845f19f44
ms.date: 04/30/2018
keywords: ["RtlEqualUnicodeString function"]
ms.keywords: RtlEqualUnicodeString, RtlEqualUnicodeString routine [Kernel-Mode Driver Architecture], k109_59d7c507-968a-4cf5-b1f0-91c8cd7ccb64.xml, kernel.rtlequalunicodestring, wdm/RtlEqualUnicodeString
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlEqualUnicodeString
 - wdm/RtlEqualUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlEqualUnicodeString
---

# RtlEqualUnicodeString function


## -description

The <b>RtlEqualUnicodeString</b> routine compares two Unicode strings to determine whether they are equal.

## -parameters

### -param String1 

[in]
Pointer to the first Unicode string.

### -param String2 

[in]
Pointer to the second Unicode string.

### -param CaseInSensitive 

[in]
If <b>TRUE</b>, case should be ignored when doing the comparison.

## -returns

<b>RtlEqualUnicodeString</b> returns <b>TRUE</b> if the two Unicode strings are equal; otherwise, it returns <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlequalstring">RtlEqualString</a>