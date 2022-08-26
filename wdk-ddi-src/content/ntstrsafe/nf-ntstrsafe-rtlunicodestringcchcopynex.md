---
UID: NF:ntstrsafe.RtlUnicodeStringCchCopyNEx
title: RtlUnicodeStringCchCopyNEx function (ntstrsafe.h)
description: The RtlUnicodeStringCchCopyNEx function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string.
old-location: kernel\rtlunicodestringcchcopynex.htm
tech.root: kernel
ms.date: 08/26/2022
keywords: ["RtlUnicodeStringCchCopyNEx function"]
ms.keywords: RtlUnicodeStringCchCopyNEx, RtlUnicodeStringCchCopyNEx function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringcchcopynex, ntstrsafe/RtlUnicodeStringCchCopyNEx, safestrings_e87c890a-b794-41c0-b506-b2b29902339c.xml
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows XP with Service Pack 1 (SP1).
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
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUnicodeStringCchCopyNEx
 - ntstrsafe/RtlUnicodeStringCchCopyNEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ntstrsafe.lib
 - Ntstrsafe.dll
api_name:
 - RtlUnicodeStringCchCopyNEx
---

# RtlUnicodeStringCchCopyNEx function

## -description

The **RtlUnicodeStringCchCopyNEx** function copies a string from one [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure to another while limiting the size of the copied string.

## -parameters

### -param DestinationString [out]

Optional. A pointer to a **UNICODE_STRING** structure that receives the copied string. The string that the *SourceString* parameter's **UNICODE_STRING** structure points to is copied to the buffer that the *DestinationString* parameter's **UNICODE_STRING** structure points to. The maximum number of characters in the structure's string buffer is NTSTRSAFE_UNICODE_STRING_MAX_CCH. *DestinationString* can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param SourceString [in]

Optional. A pointer to a **UNICODE_STRING** structure that contains the string to be copied. The maximum number of characters in the structure's string buffer is `NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR)`. *SourceString* can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param cchToCopy [in]

The number of characters to be copied from the source to the destination.

### -param RemainingString [out, optional]

Optional. If the caller supplies a non-**NULL** pointer to a **UNICODE_STRING** structure, the function sets this structure's **Buffer** member to the end of the concatenated string, sets the structure's **Length** member to zero, and sets the structure's **MaximumLength** member to the number of bytes that are remaining in the destination buffer. *RemainingString* can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows:

<table>
  <tr>
    <th>Value</th>
    <th>Meaning</th>
  </tr>
  <tr>
    <td><b>STRSAFE_FILL_BEHIND</b></td>
    <td>
      If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the last character in the string.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_IGNORE_NULLS</b></td>
    <td>
      If this flag is set, the source or destination pointer, or both, can be <b>NULL</b>. <b>RtlUnicodeStringCchCopyNEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied. <b>NULL</b> destination buffer pointers cannot receive nonempty strings.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_FILL_ON_FAILURE</b></td>
    <td>
      If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer. This operation overwrites any preexisting buffer contents.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_NULL_ON_FAILURE</b></td>
    <td>
      If this flag is set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_NO_TRUNCATION</b></td>
    <td>
      <p>If this flag is set and the function returns STATUS_BUFFER_OVERFLOW:</p>
      <ul>
        <li>If <b>STRSAFE_FILL_ON_FAILURE</b> is also specified, <b>STRSAFE_NO_TRUNCATION</b> fills the destination buffer accordingly.</li>
        <li>Otherwise, the contents of the destination buffer will be set to an empty string, even if <b>STRSAFE_NULL_ON_FAILURE</b> is not set. <b>STRSAFE_FILL_BEHIND_NULL</b> is ignored.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_ZERO_LENGTH_ON_FAILURE</b></td>
    <td>
      If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the destination string length is set to zero bytes.
    </td>
  </tr>
</table>

## -returns

**RtlUnicodeStringCchCopyNEx** returns one of the following NTSTATUS values.

<table>
  <tr>
    <th>Return code</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><b>STATUS_SUCCESS</b></td>
    <td>
      This <i>success</i> status means source data was present, and the strings were concatenated without truncation.
    </td>
  </tr>
  <tr>
    <td><b>STATUS_BUFFER_OVERFLOW</b></td>
    <td>
      This <i>warning</i> status means that the copy operation did not complete because of insufficient space in the
      destination buffer. If <b>STRSAFE_NO_TRUNCATION</b> is set in <i>dwFlags</i>, the destination buffer is not modified. If
      the flag is not
      set, the destination buffer contains a truncated version of the copied string.
    </td>
  </tr>
  <tr>
    <td><b>STATUS_INVALID_PARAMETER</b></td>
    <td>
      This <i>error</i> status means that the function received an invalid input parameter. For more information, see
      the following list.
    </td>
  </tr>
</table>

**RtlUnicodeStringCchCopyNEx** returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

- The contents of a **UNICODE_STRING** structure are invalid.
- An invalid flag is specified in *dwFlags*.
- The destination buffer is already full.
- A buffer pointer is **NULL** and the STRSAFE_IGNORE_NULLS flag is not specified in *dwFlags*.
- The destination buffer pointer is **NULL**, but the buffer size is not zero.
- The destination buffer pointer is **NULL**, or its length is zero, but a nonzero length source string is present.
- The *cchToCopy* parameter's value is greater than NTSTRSAFE_UNICODE_STRING_MAX_CCH.

For information about how to test NTSTATUS values, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The **RtlUnicodeStringCchCopyNEx** function uses the destination buffer's size to ensure that the copy operation does not write past the end of the buffer. By default, the function does *not* terminate the resultant string with a null character value (that is, with zero). As an option, the caller can use the STRSAFE_FILL_BEHIND flag and a fill byte value of zero to null-terminate a resultant string that does not occupy the entire destination buffer.

**RtlUnicodeStringCchCopyNEx** adds to the functionality of the [RtlUnicodeStringCchCopyN](./nf-ntstrsafe-rtlunicodestringcchcopyn.md) function by returning a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that identifies the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to **RtlUnicodeStringCchCopyNEx** for additional control.

If the source and destination strings overlap, the behavior of the function is undefined.

The *SourceString* and *DestinationString* pointers cannot be **NULL** unless the STRSAFE_IGNORE_NULLS flag is set in *dwFlags*. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be **NULL**. If the *DestinationString* pointer is **NULL**, the *SourceString* pointer must be **NULL** or the **UNICODE_STRING** structure must contain an empty string.

For more information about the safe string functions, see [Using safe string functions](/windows-hardware/drivers/kernel/using-safe-string-functions).

## -see-also

- [RtlUnicodeStringCbCopyNEx](./nf-ntstrsafe-rtlunicodestringcbcopynex.md)
- [RtlUnicodeStringCchCopyN](./nf-ntstrsafe-rtlunicodestringcchcopyn.md)
- [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
