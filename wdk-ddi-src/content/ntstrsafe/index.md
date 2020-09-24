---
UID: NA:ntstrsafe
title: Ntstrsafe.h header
ms.assetid: 65f21332-b24f-3667-9a7a-dd2844d95ae9
ms.date: 05/09/2018
keywords: ["Ntstrsafe.h header"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: kernel
f1_keywords:
 - ntstrsafe
 - ntstrsafe/ntstrsafe
---

# Ntstrsafe.h header


## -description

If you use the safe string functions instead of the string manipulation functions that are provided by C-language run-time libraries, you protect your code from buffer overrun errors that can make code untrustworthy. This header declares functions that copy, concatenate, and format strings in a manner that prevents buffer overrun errors.

To manipulate Unicode and ANSI strings, each function is available in two versions:

- A W-suffixed version that supports two-byte Unicode characters.
- An A-suffixed version that supports one-byte ANSI characters.

Unicode strings are specified within [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structures in kernel-mode drivers.


For more information, see:

- [Using Safe String Functions](/windows-hardware/drivers/kernel/using-safe-string-functions)