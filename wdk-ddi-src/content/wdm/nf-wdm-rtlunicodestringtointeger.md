---
UID: NF:wdm.RtlUnicodeStringToInteger
title: RtlUnicodeStringToInteger function (wdm.h)
description: The RtlUnicodeStringToInteger routine converts a Unicode string representation of a number to the equivalent integer value.
old-location: kernel\rtlunicodestringtointeger.htm
tech.root: kernel
ms.date: 11/09/2021
keywords: ["RtlUnicodeStringToInteger function"]
ms.keywords: RtlUnicodeStringToInteger, RtlUnicodeStringToInteger routine [Kernel-Mode Driver Architecture], k109_862feacf-64af-4aae-87b5-264ef277ea22.xml, kernel.rtlunicodestringtointeger, wdm/RtlUnicodeStringToInteger
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
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
req.lib: NtosKrnl.lib (kernel mode); Ntdll.lib (user mode)
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUnicodeStringToInteger
 - wdm/RtlUnicodeStringToInteger
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlUnicodeStringToInteger
---

# RtlUnicodeStringToInteger function

## -description

The **RtlUnicodeStringToInteger** routine converts a Unicode string representation of a number to the equivalent integer value.

## -parameters

### -param String [in]

A pointer to a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the number representation to convert to the equivalent integer value.

### -param Base [in, optional]

A numeric value that indicates the base (or radix) of the number that the Unicode string represents. This parameter value is optional and can be set to zero.

If *Base* is zero, **RtlUnicodeStringToInteger** checks the prefix of the Unicode string to determine the base of the number:

- If the prefix is "0x", **RtlUnicodeStringToInteger** interprets the number in the string as a hexadecimal integer.

- If the prefix is "0o", **RtlUnicodeStringToInteger** interprets the number in the string as an octal integer.

- If the prefix is "0b", **RtlUnicodeStringToInteger** interprets the number in the string as a binary integer.

If the Unicode string does not contain any of these prefixes, **RtlUnicodeStringToInteger** treats the string as a base-10 integer.

### -param Value [out]

A pointer to a ULONG variable to which **RtlUnicodeStringToInteger** writes the integer value that results from conversion of the Unicode string.

## -returns

If the conversion is successful, the **RtlUnicodeStringToInteger** routine returns STATUS_SUCCESS and sets **Value* to the integer value represented by the number in the Unicode string. If the string is not empty, but does not start with a valid number representation, the routine returns STATUS_SUCCESS and sets **Value* to zero. If the string is empty, the routine fails and returns STATUS_INVALID_PARAMETER.

## -remarks

This routine skips any white space at the start of the input string to find the start of the number.

If the first non-white space character in the string is a hyphen (-), the integer value written to **Value* is negative; otherwise, if the first character is a "+" or there is no sign character, the integer value written to **Value* is positive.

 If the string does not contain a valid number, or if the first digit in the string is preceded by a non-white space character other than '+' or '-', the routine sets the output value to zero and returns STATUS_SUCCESS.

A substring that contains one or more valid digits is terminated by any character that is not a valid digit. For example, if *Base* = 2, valid digits are '0' and '1'. If *Base* = 8, valid digits are '0' to '7'. If *Base* = 10, valid digits are '0' to '9'. If *Base* = 16, valid digits are '0' to '9', 'a' to 'f', and 'A' to 'F'.

The following table contains examples of output values that result from various combinations of input strings and *Base* parameter values.

| Input string | Base | Output value |
|--|--|--|
| "123" | 10 | 123 |
| "-345" | 10 | -345 |
| "xyz" | 10 | 0 |
| "+678abc" | 10 | 678 |
| "+678abc" | 16 | 6785724 |
| "007" | 10 | 7 |
| "789" | 8 | 7 |
| "FGH" | 16 | 15 |
| " " | 10 | 0 |

A related routine, [RtlIntegerToUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlintegertounicodestring), converts an integer value to the equivalent Unicode string representation.

## -see-also

[RtlIntegerToUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlintegertounicodestring)

[UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
