---
UID: NF:ntifs.RtlUnicodeStringToUTF8String
title: RtlUnicodeStringToUTF8String function
author: windows-driver-content
description: RtlUnicodeStringToUTF8String converts the specified Unicode string to a UTF-8 string.
tech.root: ifsk
ms.assetid: 8c1e181a-7737-4e26-8fc1-a00ed16673e9
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: function
ms.keywords: RtlUnicodeStringToUTF8String
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - RtlUnicodeStringToUTF8String
 - ntifs/RtlUnicodeStringToUTF8String
topic_type:
 - apiref
api_type:
 - 
api_location:
 - 
api_name:
 - RtlUnicodeStringToUTF8String
product:
 - Windows
---

# RtlUnicodeStringToUTF8String function (ntifs.h)


## -description

**RtlUnicodeStringToUTF8String** converts the specified Unicode string into a UTF-8 string.

## -parameters

### -param DestinationString

Pointer to the buffer in which the converted output UTF-8 string is placed. The *DestinationString->MaximumLength* field is set only if **AllocateDestinationString** is TRUE.

### -param SourceString

Pointer to the Unicode string to be converted to UTF-8.

### -param AllocateDestinationString

Boolean value. When set TRUE, **RtlUnicodeStringToUTF8String** allocates the buffer space for the destination string. Only storage for *DestinationString->Buffer* is allocated by this API. If **RtlUnicodeStringToUTF8String** does the buffer allocation, then the caller must deallocate the buffer using [**RtlFreeUTF8String**](nf-ntifs-rtlfreeutf8string.md).

## -returns

This function returns STATUS_SUCCESS when the conversion is successful. Possible error or warning codes include:

| Code                        | Description |
| --------------------------- | ----------- |
| STATUS_INVALID_PARAMETER*X* | Error: One of the parameter values is invalid. |
| STATUS_NO_MEMORY            | Error: **RtlUnicodeStringToUTF8String** was unable to allocate buffer space. |
| STATUS_BUFFER_OVERFLOW      | Warning: The converted string in *DestinationString->Buffer* is truncated due to insufficient space in the destination buffer. |
| STATUS_SOME_NOT_MAPPED     | Warning: The call was successful, but one or more of the input characters were invalid and were replaced by the Unicode replacement character, U+FFFD, before being converted to UTF-8. |

## -remarks

The UTF-8 output string is null-terminated only if the Unicode input string is null-terminated.

**RtlUnicodeStringToUTF8String** supports Unicode surrogate pairs. However, a surrogate leading word value that is not followed by a trailing word value, or a trailing word value that is not preceded by a leading word value, is not recognized as a valid character code and is replaced by the Unicode replacement character, U+FFFD.

**RtlUnicodeStringToUTF8String** continues to convert the input string to an output string until it reaches the end of the source buffer or the end of the destination buffer, whichever occurs first. The routine converts any null characters in the input string to null characters in the output string. If the input string contains a terminating null character, but the null character is not located at the end of the source buffer, the routine continues past the terminating null character until it reaches the end of the available buffer space.

The [**RtlUTF8StringToUnicodeString**](nf-ntifs-rtlutf8stringtounicodestring.md) routine converts a UTF-8 string to a Unicode string.

You can use the **RtlUnicodeStringToUTF8String** and [**RtlUTF8StringToUnicodeString**]((nf-ntifs-rtlutf8stringtounicodestring.md)) routines to perform a lossless conversion of valid text strings between the Unicode and UTF-8 formats. However, strings that have arbitrary data values are likely to violate the Unicode rules for encoding surrogate pairs, and any information that is contained in the invalid values in an input string is lost and cannot be recovered from the resulting output string.

## -see-also

[**RtlFreeUTF8String**](nf-ntifs-rtlfreeutf8string.md)

[**RtlUTF8StringToUnicodeString**](nf-ntifs-rtlutf8stringtounicodestring.md)

