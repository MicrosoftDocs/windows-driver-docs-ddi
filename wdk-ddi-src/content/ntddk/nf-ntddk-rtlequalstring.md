---
UID: NF:ntddk.RtlEqualString
title: RtlEqualString function (ntddk.h)
description: The RtlEqualString routine compares two counted strings to determine whether they are equal.
old-location: kernel\rtlequalstring.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlEqualString function"]
ms.keywords: RtlEqualString, RtlEqualString routine [Kernel-Mode Driver Architecture], k109_67ef861f-4f4b-4e98-be53-8962b02df08e.xml, kernel.rtlequalstring, ntddk/RtlEqualString
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
 - RtlEqualString
 - ntddk/RtlEqualString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlEqualString
---

# RtlEqualString function


## -description

The <b>RtlEqualString</b> routine compares two counted strings to determine whether they are equal.

## -parameters

### -param String1 [in]


Pointer to the first string.

### -param String2 [in]


Pointer to the second string.

### -param CaseInSensitive [in]


If <b>TRUE</b>, case should be ignored when doing the comparison.

## -returns

<b>RtlEqualString</b> returns <b>TRUE</b> if the two strings are equal, otherwise it returns <b>FALSE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlequalunicodestring">RtlEqualUnicodeString</a>
