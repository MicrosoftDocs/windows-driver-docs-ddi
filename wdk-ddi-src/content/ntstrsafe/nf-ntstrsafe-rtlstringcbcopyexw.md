---
UID: NF:ntstrsafe.RtlStringCbCopyExW
title: RtlStringCbCopyExW function (ntstrsafe.h)
description: Learn how the RtlStringCbCopyExW and RtlStringCbCopyExA functions copy a byte-counted string into a buffer.
old-location: kernel\rtlstringcbcopyex.htm
tech.root: kernel
ms.date: 08/26/2022
keywords: ["RtlStringCbCopyExW function"]
ms.keywords: RtlStringCbCopyEx, RtlStringCbCopyExA, RtlStringCbCopyExW, RtlStringCbCopyExW function [Kernel-Mode Driver Architecture], STRSAFE_FILL_BEHIND_NULL, STRSAFE_FILL_ON_FAILURE, STRSAFE_IGNORE_NULLS, STRSAFE_NO_TRUNCATION, STRSAFE_NULL_ON_FAILURE, kernel.rtlstringcbcopyex, ntstrsafe/RtlStringCbCopyExA, ntstrsafe/RtlStringCbCopyExW, safestrings_f0187c41-23b0-491b-9154-ff8778b06418.xml
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbCopyExW (Unicode) and RtlStringCbCopyExA (ANSI)
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
 - RtlStringCbCopyExW
 - ntstrsafe/RtlStringCbCopyExW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ntstrsafe.lib
 - Ntstrsafe.dll
api_name:
 - RtlStringCbCopyExW
---

# RtlStringCbCopyExW function

## -description

The **RtlStringCbCopyExW** and **RtlStringCbCopyExA** functions copy a byte-counted string into a buffer.

## -parameters

### -param pszDest [out, optional]

A pointer to a caller-supplied buffer that receives the copied string. The string at *pszSrc* is copied to the buffer at *pszDest* and terminated with a null character. The *pszDest* pointer can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param cbDest [in]

The size, in bytes, of the destination buffer. The buffer must be large enough for the string and the terminating null character.

For Unicode strings, the maximum number of bytes is `NTSTRSAFE_MAX_CCH * sizeof(WCHAR)`

For ANSI strings, the maximum number of bytes is `NTSTRSAFE_MAX_CCH * sizeof(char)`

If *pszDest* is **NULL**, *cbDest* must be zero.

### -param pszSrc [in, optional]

A pointer to a caller-supplied, null-terminated string. The *pszSrc* pointer can be **NULL**, but only if STRSAFE_IGNORE_NULLS is set in *dwFlags*.

### -param ppszDestEnd [out, optional]

If the caller supplies a non-**NULL** address pointer, then after the copy operation completes, the function loads that address with a pointer to the destination buffer's resulting **NULL** string terminator.

### -param pcbRemaining [out, optional]

If the caller supplies a non-**NULL** address pointer, the function loads the address with the number of unused bytes that are in the buffer pointed to by *pszDest*, including bytes used for the terminating null character.

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
      If set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination
      buffer that follows the terminating null character.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_IGNORE_NULLS</b></td>
    <td>
      If set, either <i>pszDest</i> or <i>pszSrc</i>, or both, can be <b>NULL</b>. <b>NULL</b> <i>pszSrc</i> pointers
      are treated like empty strings (TEXT("")), which can be copied. <b>NULL</b> <i>pszDest</i> pointers cannot receive
      nonempty strings.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_FILL_ON_FAILURE</b></td>
    <td>
      If set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and
      the buffer is null-terminated. This operation overwrites any preexisting buffer contents.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_NULL_ON_FAILURE</b></td>
    <td>
      If set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation
      overwrites any preexisting buffer contents.
    </td>
  </tr>
  <tr>
    <td><b>STRSAFE_NO_TRUNCATION</b></td>
    <td>
      <p>If set and the function returns STATUS_BUFFER_OVERFLOW:</p>
      <ul>
        <li>If <b>STRSAFE_FILL_ON_FAILURE</b> is also specified, <b>STRSAFE_NO_TRUNCATION</b> fills the destination
          buffer accordingly.</li>
        <li>Otherwise, the contents of the destination buffer will be set to an empty string, even if
          <b>STRSAFE_NULL_ON_FAILURE</b> is not set. <b>STRSAFE_FILL_BEHIND_NULL</b> is ignored.</li>
      </ul>
    </td>
  </tr>
</table>

## -returns

The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

<table>
  <tr>
    <th>Return code</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>
      <b>STATUS_SUCCESS</b>
    </td>
    <td>
      This <i>success</i> status means source data was present, the string was copied without truncation, and the
      resultant destination buffer is null-terminated.
    </td>
  </tr>
  <tr>
    <td>
      <b>STATUS_BUFFER_OVERFLOW</b>
    </td>
    <td>
      This <i>warning</i> status means the copy operation did not complete due to insufficient space in the destination
      buffer. If <b>STRSAFE_NO_TRUNCATION</b> is set, see the <i>dwFlags</i> parameter for more information.
    </td>
  </tr>
  <tr>
    <td>
      <b>STATUS_INVALID_PARAMETER</b>
    </td>
    <td>
      <p>This <i>error</i> status means the function received an invalid input parameter. For more information, see the
        following paragraph.</p>
      <p>The function returns the STATUS_INVALID_PARAMETER value when:</p>
      <ul>
        <li>An invalid flag was specified.</li>
        <li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
        <li>The destination buffer was already full.</li>
        <li>A <b>NULL</b> pointer was present without the STRSAFE_IGNORE_NULLS flag.</li>
        <li>The destination buffer pointer was <b>NULL</b>, but the buffer size was not zero.</li>
        <li>The destination buffer pointer was <b>NULL</b>, or its length was zero, but a nonzero length source string
          was present.</li>
      </ul>
    </td>
  </tr>
</table>

## -remarks

**RtlStringCbCopyExA** and **RtlStringCbCopyExW** should be used instead of the following functions:

- **strcpy**
- **wcscpy**

The size, in bytes, of the destination buffer is provided to **RtlStringCbCopyExA** and **RtlStringCbCopyExW** to ensure that they do not write past the end of the buffer.

**RtlStringCbCopyEx** adds to the functionality of [RtlStringCbCopy](./nf-ntstrsafe-rtlstringcbcopya.md) by returning a pointer to the end of the destination string as well as the number of bytes left unused in that string. Flags can be passed to the function for additional control.

Use **RtlStringCbCopyExW** to handle Unicode strings and  **RtlStringCbCopyExA** to handle ANSI strings. The form you use depends on your data as shown in the following table.

| String data type | String literal | Function |
|--|--|--|
| **WCHAR** | L"string" | **RtlStringCbCopyExW** |
| **char** | "string" | **RtlStringCbCopyExA** |

If *pszSrc* and *pszDest* point to overlapping strings, the behavior of the function is undefined.

Neither *pszSrc* nor *pszDest* can be **NULL** unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be **NULL**. If *pszDest* is **NULL**, *pszSrc* must either be **NULL** or point to an empty string.

For more information about the safe string functions, see [Using safe string functions](/windows-hardware/drivers/kernel/using-safe-string-functions).

## -see-also

- [RtlStringCbCopy](./nf-ntstrsafe-rtlstringcbcopya.md)
- [RtlStringCchCopyEx](./nf-ntstrsafe-rtlstringcchcopyexa.md)
