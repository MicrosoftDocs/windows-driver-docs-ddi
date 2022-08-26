---
UID: NF:ntstrsafe.RtlStringCchCopyUnicodeStringEx
title: RtlStringCchCopyUnicodeStringEx function (ntstrsafe.h)
description: The RtlStringCchCopyUnicodeStringEx function copies the contents of a UNICODE_STRING structure to a specified destination.
old-location: kernel\rtlstringcchcopyunicodestringex.htm
tech.root: kernel
ms.date: 08/26/2022
keywords: ["RtlStringCchCopyUnicodeStringEx function"]
ms.keywords: RtlStringCchCopyUnicodeStringEx, RtlStringCchCopyUnicodeStringEx function [Kernel-Mode Driver Architecture], kernel.rtlstringcchcopyunicodestringex, ntstrsafe/RtlStringCchCopyUnicodeStringEx, safestrings_fd016973-3ea3-432d-80dc-f23a3821d607.xml
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
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
 - RtlStringCchCopyUnicodeStringEx
 - ntstrsafe/RtlStringCchCopyUnicodeStringEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ntstrsafe.lib
 - Ntstrsafe.dll
api_name:
 - RtlStringCchCopyUnicodeStringEx
---

# RtlStringCchCopyUnicodeStringEx function

## -description

The **RtlStringCchCopyUnicodeStringEx** function copies the contents of a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure to a specified destination.

## -parameters

### -param pszDest [out]

Optional. A pointer to a buffer that receives the copied string. The string that the *SourceString* parameter's **UNICODE_STRING** structure points to is copied to the buffer at *pszDest* and terminated with a null character. This pointer can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param cchDest [in]

The size, in characters, of the destination buffer. The buffer must be large enough for the string and the terminating null character. The maximum number of characters in the buffer is NTSTRSAFE_MAX_CCH.

### -param SourceString [in]

Optional. A pointer to a **UNICODE_STRING** structure that contains the string to be copied. The maximum number of characters in the string is NTSTRSAFE_UNICODE_STRING_MAX_CCH. This pointer can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param ppszDestEnd [out]

Optional. If the caller supplies a non-**NULL** address pointer, then after the copy operation completes, the function loads that address with a pointer to the destination buffer's resulting null string terminator.

### -param pcchRemaining [out, optional]

Optional. If the caller supplies a non-**NULL** address pointer, the function loads the address with the number of unused characters that are in the buffer that *pszDest* points to, including the terminating null character.

### -param dwFlags [in]

One or more flags and, optionally, a fill byte. The flags are defined as follows:

<table>
  <tr>
    <th>Value</th>
    <th>Meaning</th>
  </tr>
  <tr>
    <td><b>STRSAFE_FILL_BEHIND_NULL</b></td>
    <td>
      If this flag is set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the terminating null character.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_IGNORE_NULLS</b></td>
    <td>
      If this flag is set, either the source or destination pointer, or both, can be <b>NULL</b>. <b>RtlStringCchCopyUnicodeStringEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")), which can be copied. <b>NULL</b> destination buffer pointers cannot receive nonempty strings.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_FILL_ON_FAILURE</b></td>
    <td>
      If this flag is set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and the buffer is null-terminated. This operation overwrites any preexisting buffer contents.
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
</table>

## -returns

**RtlStringCchCopyUnicodeStringEx** returns one of the following NTSTATUS values.

<table>
  <tr>
    <th>Return code</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><b>STATUS_SUCCESS</b></td>
    <td>
      This <i>success</i> status means that source data was present, the string was copied without truncation, and the
      resultant destination buffer is null-terminated.
    </td>
  </tr>
  <tr>
    <td><b>STATUS_BUFFER_OVERFLOW</b></td>
    <td>
      This <i>warning</i> status means that the copy operation did not complete because of insufficient space in the
      destination buffer. If <b>STRSAFE_NO_TRUNCATION</b> is set in <i>dwFlags</i>, the destination buffer is not modified. If
      the flag is not set, the destination buffer contains a truncated version of the copied string.
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

**RtlStringCchCopyUnicodeStringEx** returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

- The contents of the **UNICODE_STRING** structure are invalid.
- An invalid flag is specified in *dwFlags*.
- The value in *cchDest* is larger than the maximum buffer size.
- The destination buffer (which *pszDest* points to) is already full.
- A buffer pointer is **NULL** and the STRSAFE_IGNORE_NULLS flag is not specified.
- The destination buffer pointer is **NULL**, but the buffer size is not zero.
- The destination buffer pointer is **NULL** or its length is zero, but a nonzero length source string is present.

For information about how to test NTSTATUS values, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The **RtlStringCchCopyUnicodeStringEx** function uses the destination buffer's size (which the *cchDest* parameter specifies) to ensure that the copy operation does not write past the end of the buffer.

**RtlStringCchCopyUnicodeStringEx** adds to the functionality of the [RtlStringCchCopyUnicodeString](./nf-ntstrsafe-rtlstringcchcopyunicodestring.md) function by returning a pointer to the end of the destination string and the number of bytes that are left unused in that string. You can pass flags to the function for additional control.

If the source and destination strings overlap, the behavior of the function is undefined.

The *SourceString *and *pszDest* pointers cannot be **NULL** unless the STRSAFE_IGNORE_NULLS flag is set in *dwFlags*. If STRSAFE_IGNORE_NULLS is set, one or both of these points can be **NULL**. If the *pszDest* pointer is **NULL**, the *SourceString* pointer must be **NULL** or the [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure must describe an empty string.

For more information about the safe string functions, see [Using safe string functions](/windows-hardware/drivers/kernel/using-safe-string-functions).

## -see-also

- [RtlStringCbCopyUnicodeStringEx](./nf-ntstrsafe-rtlstringcbcopyunicodestringex.md)
- [RtlStringCchCopyUnicodeString](./nf-ntstrsafe-rtlstringcchcopyunicodestring.md)
- [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
