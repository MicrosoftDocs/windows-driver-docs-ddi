---
UID: NF:wdm.RtlInitAnsiString
title: RtlInitAnsiString function (wdm.h)
description: The RtlInitAnsiString routine initializes a counted string of ANSI characters.
tech.root: kernel
ms.date: 12/13/2022
keywords: ["RtlInitAnsiString function"]
ms.keywords: RtlInitAnsiString, RtlInitAnsiString routine [Kernel-Mode Driver Architecture], k109_733e2861-a19a-41ca-92cc-d50caa8beead.xml, kernel.rtlinitansistring, wdm/RtlInitAnsiString
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlInitAnsiString
 - wdm/RtlInitAnsiString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlInitAnsiString
---

## -description

The **RtlInitAnsiString** routine initializes a counted string of ANSI characters.

## -parameters

### -param DestinationString [out]

A pointer to the [ANSI_STRING](/windows/win32/api/ntdef/ns-ntdef-string) structure to be initialized.

### -param SourceString [in, optional]

A pointer to a null-terminated character string. This string is used to initialize the counted string pointed to by *DestinationString*.

## -returns

None

## -remarks

This routine initializes a counted character string.

The routine copies the *SourceString* pointer value to the **Buffer** member of the [ANSI_STRING](/windows/win32/api/ntdef/ns-ntdef-string) structure pointed to by *DestinationString*. The **Length** member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The **MaximumLength** member of the structure is set to the length, in bytes, of the source string, including the terminating null. If *SourceString* is **NULL**, **Length** and **MaximumLength** are both set to zero.

**RtlInitAnsiString** does not alter the source string pointed to by *SourceString*.

If the source string is longer than MAXUSHORT - 1 bytes, **RtlInitAnsiString** sets the **Length** member of the **ANSI_STRING** structure pointed to by *DestinationString* to MAXUSHORT - 1, and sets the **MaximumLength** member of this structure to MAXUSHORT.  In this case, the **Length** and **MaximumLength** values misrepresent the length of the null-terminated source string, and relying on the accuracy of these values is potentially dangerous.

Callers of **RtlInitAnsiString** can be running at IRQL <= DISPATCH_LEVEL if the *DestinationString* buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other **Rtl*Xxx*String** routines cannot be called at IRQL > PASSIVE_LEVEL.

The **RTL_CONSTANT_STRING** macro creates a string or Unicode string structure to hold a counted string.

```cpp
STRING RTL_CONSTANT_STRING(
  [in]  PCSZ SourceString
);

UNICODE_STRING RTL_CONSTANT_STRING(
  [in]  PCWSTR SourceString
);
```

**RTL_CONSTANT_STRING** returns either a string structure or Unicode string structure.

The **RTL_CONSTANT_STRING** macro replaces the **RtlInitAnsiString**, [RtlInitString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitstring), and [RtlInitUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring) routines when passing a constant string.

You can use **RTL_CONSTANT_STRING** to initialize global variables.

## -see-also

[ANSI_STRING](/windows/win32/api/ntdef/ns-ntdef-string)
