---
UID: NF:ntstrsafe.RtlUnicodeStringCatStringEx
title: RtlUnicodeStringCatStringEx function (ntstrsafe.h)
description: The RtlUnicodeStringCatStringEx function concatenates two strings when the destination string is contained in a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringcatstringex.htm
tech.root: kernel
ms.date: 08/25/2022
keywords: ["RtlUnicodeStringCatStringEx function"]
ms.keywords: RtlUnicodeStringCatStringEx, RtlUnicodeStringCatStringEx function [Kernel-Mode Driver Architecture], kernel.rtlunicodestringcatstringex, ntstrsafe/RtlUnicodeStringCatStringEx, safestrings_7ca374c5-13a0-4fe6-ab53-7770bc8ef9c3.xml
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
 - RtlUnicodeStringCatStringEx
 - ntstrsafe/RtlUnicodeStringCatStringEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ntstrsafe.lib
 - Ntstrsafe.dll
api_name:
 - RtlUnicodeStringCatStringEx
---

# RtlUnicodeStringCatStringEx function

## -description

The **RtlUnicodeStringCatStringEx** function concatenates two strings when the destination string is contained in a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure.

## -parameters

### -param DestinationString [in, out]

Optional. A pointer to a **UNICODE_STRING** structure. This structure includes a buffer that, on input, contains a destination string to which the source string will be concatenated. On output, this buffer is the destination buffer that contains the entire resultant string. The source string (excluding the terminating null) is added to the end of the destination string. The maximum number of bytes in the structure's string buffer is `NTSTRSAFE_UNICODE_STRING_MAX_CCH * sizeof(WCHAR)`. *DestinationString* can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param pszSrc [in]

Optional. A caller-supplied pointer to a null-terminated source string. This string will be concatenated to the end of the string that is contained in the **UNICODE_STRING** structure that *DestinationString* specifies. *pszSrc* can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param RemainingString [out, optional]

Optional. If the caller supplies a non-**NULL** pointer to a **UNICODE_STRING** structure, the function sets this structure's **Buffer** member to the end of the concatenated string, sets the structure's **Length** member to zero, and sets the structure's **MaximumLength** member to the number of bytes that are remaining in the destination buffer. This pointer can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

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
      If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the
      destination buffer that follows the last character in the string.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_IGNORE_NULLS</b></td>
    <td>
      If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the
      destination buffer that follows the last character in the string.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_FILL_ON_FAILURE</b></td>
    <td>
      If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination
      buffer. This operation overwrites any preexisting buffer contents.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_NULL_ON_FAILURE</b></td>
    <td>
      If this flag is set and the function fails, the destination buffer is set to an empty string (TEXT("")). This
      operation overwrites any preexisting buffer contents.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_NO_TRUNCATION</b></td>
    <td>
      <p>If set and the function returns STATUS_BUFFER_OVERFLOW:</p>
      <ul>
        <li>If STRSAFE_FILL_ON_FAILURE is also specified, STRSAFE_NO_TRUNCATION fills the destination buffer
          accordingly.</li>
        <li>Otherwise, the destination buffer will be unmodified.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_ZERO_LENGTH_ON_FAILURE</b></td>
    <td>
      If this flag is set and the function returns STATUS_BUFFER_OVERFLOW, the destination string length is set to zero
      bytes.
    </td>
  </tr>
</table>

## -returns

**RtlUnicodeStringCatStringEx** returns one of the following NTSTATUS values.

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | This *success* status means source data was present, and the strings were concatenated without truncation. |
| **STATUS_BUFFER_OVERFLOW** | This *warning* status means that the copy operation did not complete because of insufficient space in the destination buffer. If **STRSAFE_NO_TRUNCATION** is set, see the *dwFlags* parameter for more information. |
| **STATUS_INVALID_PARAMETER** | This *error* status means that the function received an invalid input parameter. For more information, see the following list. |

**RtlUnicodeStringCatStringEx** returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

- The contents of a **UNICODE_STRING** structure are invalid.
- An invalid flag is specified in *dwFlags*.
- The destination buffer is already full.
- A buffer pointer is **NULL** and the STRSAFE_IGNORE_NULLS flag is not specified in *dwFlags*.
- The destination buffer pointer is **NULL**, but the buffer size is not zero.
- The destination buffer pointer is **NULL**, or its length is zero, but a nonzero length source string is present.

For information about how to test NTSTATUS values, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The **RtlUnicodeStringCatStringEx** function uses the destination buffer's size to ensure that the concatenation operation does not write past the end of the buffer. By default, the function does *not* terminate the resultant string with a null character value (that is, with zero). As an option, the caller can use the STRSAFE_FILL_BEHIND flag and a fill byte value of zero to null-terminate a resultant string that does not occupy the entire destination buffer.

**RtlUnicodeStringCatStringEx** adds to the functionality of the [RtlUnicodeStringCatString](./nf-ntstrsafe-rtlunicodestringcatstring.md) function by returning a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that identifies the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to **RtlUnicodeStringCatStringEx**or additional control.

If the source and destination strings overlap, the behavior of the function is undefined.

The *pszSrc* and *DestinationString* pointers cannot be **NULL** unless the STRSAFE_IGNORE_NULLS flag is set in *dwFlags*. If STRSAFE_IGNORE_NULLS is set, one or both of these pointers can be **NULL**. If the *DestinationString* pointer is **NULL**, the *pszSrc* pointer must either be **NULL** or point to an empty string.

For more information about the safe string functions, see [Using safe string functions](/windows-hardware/drivers/kernel/using-safe-string-functions).

## -see-also

- [RtlUnicodeStringCatString](./nf-ntstrsafe-rtlunicodestringcatstring.md)
- [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
