---
UID: NF:wdm.RtlAnsiStringToUnicodeString
title: RtlAnsiStringToUnicodeString function (wdm.h)
description: RtlAnsiStringToUnicodeString converts the given ANSI source string into a Unicode string.
tech.root: kernel
ms.date: 01/18/2023
keywords: ["RtlAnsiStringToUnicodeString function"]
ms.keywords: RtlAnsiStringToUnicodeString, RtlAnsiStringToUnicodeString function [Kernel-Mode Driver Architecture], k109_d27ee285-6d32-4ecb-994b-ba8a47f1e588.xml, kernel.rtlansistringtounicodestring, wdm/RtlAnsiStringToUnicodeString
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlAnsiStringToUnicodeString
 - wdm/RtlAnsiStringToUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlAnsiStringToUnicodeString
---

## -description

**RtlAnsiStringToUnicodeString** converts the given ANSI source string into a Unicode string.

## -parameters

### -param DestinationString [in, out]

Pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure to hold the converted Unicode string. If *AllocateDestinationString* is **TRUE**, the routine allocates a new buffer to hold the string data, and updates the **Buffer** member of *DestinationString* to point to the new buffer. Otherwise, the routine uses the currently-specified buffer to hold the string.

### -param SourceString [in]

Pointer to the ANSI string to be converted to Unicode.

### -param AllocateDestinationString [in]

Specifies if this routine should allocate the buffer space for the destination string. If it does, the caller must deallocate the buffer by calling [RtlFreeUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring).

## -returns

If the conversion succeeds, **RtlAnsiStringToUnicodeString** returns STATUS_SUCCESS. On failure, the routine does not allocate any memory.

## -remarks

The translation conforms to the current system locale information.

If caller sets *AllocateDestinationString* to **TRUE**, the routine replaces the **Buffer** member of *DestinationString* with a pointer to the buffer it allocates. The old value can be overwritten even when the routine returns an error status code.

This routine is not declared in a header file. However, you can copy the following declaration to your source code:

```cpp
NTSYSAPI
WCHAR
NTAPI
RtlAnsiCharToUnicodeChar(
    __inout PUCHAR *SourceCharacter
    );
```

You can use the following routines to convert single-byte and double-byte characters to Unicode characters:

- [RtlAnsiStringToUnicodeSize](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodesize)

- **RtlAnsiStringToUnicodeString**

- [RtlMultiByteToUnicodeSize](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlmultibytetounicodesize)

- [RtlMultiByteToUnicodeN](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlmultibytetounicoden)

For more information about these and other string-handling routines, see [Run-Time Library (RTL) Routines](/windows-hardware/drivers/ddi/_kernel/#run-time-library-rtl-routines).

**RtlAnsiCharToUnicodeChar** has security deficiencies. Consider using the **RtlAnsiStringToUnicodeString** routine instead.

If, on entry, **SourceCharacter* points to a one-byte buffer that contains the first byte of a two-byte character code, **RtlAnsiCharToUnicodeChar** overruns the buffer when it tries to read the second byte.

At system startup, the operating system determines the user language from the locale settings and installs the appropriate system ANSI code page. **RtlAnsiCharToUnicodeChar** uses this code page to convert a single-byte or double-byte character to the corresponding Unicode character.

If the system ANSI code page defines a single-byte character set (that is, the ANSI character set), **RtlAnsiCharToUnicodeChar** speeds up the conversion operation by simply [zero-extending](/windows-hardware/drivers/) an ANSI character in the range 0x00 to 0x7f to produce the corresponding Unicode character. The routine converts the ANSI value 0x5c to the backslash character ("\\"), even if the single-byte code page defines this character as the yen sign.

If, on entry, **SourceCharacter* points to an invalid character code, **RtlAnsiCharToUnicodeChar** returns the Unicode space character code, 0x0020. The following list shows examples of invalid character codes:

- The first byte of the character code is a value that is valid only as the second byte of a two-byte character code.

- The second byte of a two-byte character code is a value that is valid only as the first byte.

## -see-also

[**ANSI_STRING**](/windows/win32/api/ntdef/ns-ntdef-string)

[RtlAnsiStringToUnicodeSize](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodesize)

[RtlFreeUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfreeunicodestring)

[RtlInitAnsiString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitansistring)

[RtlUnicodeStringToAnsiString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlunicodestringtoansistring)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
