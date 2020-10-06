---
UID: NF:ntifs.RtlUTF8StringToUnicodeString
title: RtlUTF8StringToUnicodeString function (ntifs.h)
description: The RtlUTF8StringToUnicodeString routine converts the specified UTF-8 string to a Unicode string.
old-location: 
tech.root: ifsk
ms.assetid: aa4d6f8b-ab1b-4b13-83c8-fcc55f667d14
ms.date: 03/24/2020
ms.keywords: RtlUTF8StringToUnicodeString, RtlUTF8StringToUnicodeString routine [Kernel-Mode Driver Architecture], kernel.RtlUTF8StringToUnicodeString
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
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
 - RtlUTF8StringToUnicodeString
 - ntifs/RtlUTF8StringToUnicodeString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUTF8StringToUnicodeString
---

# RtlUTF8StringToUnicodeString function (ntifs.h)


## -description

The **RtlUTF8StringToUnicodeString** routine converts the specified UTF-8 string to a Unicode string.

## -parameters

### -param DestinationString

Pointer to the buffer in which the converted output Unicode string is stored. The *DestinationString->MaximumLength* field is set only if **AllocateDestinationString** is TRUE.

### -param SourceString

Pointer to the UTF-8 source string to be converted to Unicode.

### -param AllocateDestinationString

Boolean value. When set TRUE, **RtlUTF8StringToUnicodeString** allocates the buffer space for the destination string. Only storage for *DestinationString->Buffer* is allocated by this API. If **RtlUTF8StringToUnicodeString** does the buffer allocation, then the caller must deallocate the buffer using [**RtlFreeUnicodeString**](../wdm/nf-wdm-rtlfreeunicodestring.md).

## -returns

This function returns STATUS_SUCCESS when the conversion is successful. Possible error or warning codes include:

| Code                      | Description |
| ------------------------- | ----------- |
| STATUS_INVALID_PARAMETER*X* | Error: One of the parameter values is invalid. |
| STATUS_NO_MEMORY            | Error: **RtlUTF8StringToUnicodeString** was unable to allocate buffer space. |
| STATUS_BUFFER_OVERFLOW      | Warning: The converted string in *DestinationString->Buffer* is truncated due to insufficient space in the destination buffer. |
| STATUS_SOME_NOT_MAPPED     | Warning: The call was successful, but one or more of the input characters were invalid and were converted by the Unicode replacement character, U+FFFD, before being converted to UTF-8. |

## -remarks

The Unicode output string is null-terminated only if the UTF-8 input string is null-terminated.

**RtlUTF8StringToUnicodeString** supports Unicode surrogate pairs. However, a surrogate leading word value that is not followed by a trailing word value, or a trailing word value that is not preceded by a leading word value, is not recognized as a valid character and is replaced by the Unicode replacement character, U+FFFD.

**RtlUTF8StringToUnicodeString** continues to convert the input string to an output string until it reaches the end of the source buffer or the end of the destination buffer, whichever occurs first. The routine converts any null characters in the input string to null characters in the output string. If the input string contains a terminating null character, but the null character is not located at the end of the source buffer, the routine continues past the terminating null character until it reaches the end of the available buffer space.

The [**RtlUnicodeStringToUTF8String**](nf-ntifs-rtlunicodestringtoutf8string.md) routine converts a Unicode string to a UTF-8 string.

You can use the **RtlUTF8StringToUnicodeString** and [**RtlUnicodeStringToUTF8String**](nf-ntifs-rtlunicodestringtoutf8string.md) routines to perform a lossless conversion of valid text strings between the UTF-8 and Unicode formats. However, strings that have arbitrary data values are likely to violate the Unicode rules for encoding surrogate pairs, and any information that is contained in the invalid values in an input string is lost and cannot be recovered from the resulting output string.

## -see-also

[**RtlFreeUnicodeString**](../wdm/nf-wdm-rtlfreeunicodestring.md)

[**RtlUnicodeStringToUTF8String**](nf-ntifs-rtlunicodestringtoutf8string.md)
