---
UID: NF:ntifs.RtlUpcaseUnicodeStringToCountedOemString
title: RtlUpcaseUnicodeStringToCountedOemString function (ntifs.h)
description: Learn more about the RtlUpcaseUnicodeStringToCountedOemString function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["RtlUpcaseUnicodeStringToCountedOemString function"]
ms.keywords: RtlUpcaseUnicodeStringToCountedOemString, RtlUpcaseUnicodeStringToCountedOemString routine [Installable File System Drivers], ifsk.rtlupcaseunicodestringtocountedoemstring, ntifs/RtlUpcaseUnicodeStringToCountedOemString, rtlref_54925045-9df1-41ef-9878-030f30e2a0f1.xml
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlUpcaseUnicodeStringToCountedOemString
 - ntifs/RtlUpcaseUnicodeStringToCountedOemString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlUpcaseUnicodeStringToCountedOemString
---

# RtlUpcaseUnicodeStringToCountedOemString function

## -description

The **RtlUpcaseUnicodeStringToCountedOemString** routine translates a given Unicode source string into an uppercase counted OEM string using the current system OEM code page.

## -parameters

### -param DestinationString

Pointer to a caller-allocated buffer to receive the counted OEM string. If **AllocateDestinationString** is FALSE, the caller must also allocate a buffer for the **Buffer** member of **DestinationString** to hold the OEM data. If **AllocateDestinationString** is TRUE, **RtlUpcaseUnicodeStringToCountedOemString** allocates a buffer large enough to hold the string, passes a pointer to it in **Buffer**, and updates the length and maximum length members of **DestinationString** accordingly.

### -param SourceString [in]

Pointer to the Unicode string to be translated.

### -param AllocateDestinationString [in]

Set to TRUE if **RtlUpcaseUnicodeStringToCountedOemString** should allocate the buffer space for the **DestinationString**, FALSE otherwise. If this parameter is TRUE, the caller is responsible for freeing the buffer when it is no longer needed by calling **RtlFreeOemString**.

## -returns

**RtlUpcaseUnicodeStringToCountedOemString** returns STATUS_SUCCESS if it returns a translated string at **DestinationString**. Otherwise, no storage was allocated, nor was any conversion performed. It returns STATUS_UNMAPPABLE_CHARACTER if it cannot translate a character in the given **SourceString**.

## -remarks

**RtlUpcaseUnicodeStringToCountedOemString** returns a string that is not null-terminated. It translates the given source string using the OEM code page that was installed as the current system code page at system boot time, and converts the translated string to uppercase.

To find a best-match mapping for any special characters, such as a copyright character, in the given source string, **RtlUpcaseUnicodeStringToCountedOemString** performs the following operations:

1. Translates a copy of the Unicode string at **SourceString** into an OEM string

2. Translates the OEM string back into Unicode

3. Converts this new Unicode string to uppercase

4. Translates the uppercase Unicode string into a counted OEM string and returns it at **DestinationString**

This routine does not modify the source string.

For information about other string-handling routines, see [Run-Time Library (RTL) Routines](/windows-hardware/drivers/ddi/_kernel/#run-time-library-rtl-routines).

## -see-also

[**OEM_STRING**](/previous-versions/windows/hardware/drivers/ff558741(v=vs.85))

[**RtlFreeOemString**](nf-ntifs-rtlfreeoemstring.md)

[**RtlOemStringToCountedUnicodeString**](nf-ntifs-rtloemstringtocountedunicodestring.md)

[**RtlUnicodeStringToCountedOemString**](nf-ntifs-rtlunicodestringtocountedoemstring.md)

[**RtlUnicodeStringToOemSize**](nf-ntifs-rtlunicodestringtooemsize.md)

[**RtlUpcaseUnicodeStringToOemString**](nf-ntifs-rtlupcaseunicodestringtooemstring.md)

[**RtlUpcaseUnicodeToOemN**](nf-ntifs-rtlupcaseunicodetooemn.md)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
