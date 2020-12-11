---
UID: NF:ntifs.RtlIsValidOemCharacter
title: RtlIsValidOemCharacter function (ntifs.h)
description: The RtlIsValidOemCharacter routine determines if the specified Unicode character can be mapped to a valid OEM character.
old-location: ifsk\rtlisvalidoemcharacter.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlIsValidOemCharacter function"]
ms.keywords: RtlIsValidOemCharacter, RtlIsValidOemCharacter routine [Installable File System Drivers], ifsk.rtlisvalidoemcharacter, ntifs/RtlIsValidOemCharacter, rtlref_ebbaa5fc-63da-4eef-b8ac-be10a6e062a0.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
 - RtlIsValidOemCharacter
 - ntifs/RtlIsValidOemCharacter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlIsValidOemCharacter
---

# RtlIsValidOemCharacter function


## -description

The <b>RtlIsValidOemCharacter</b> routine determines if the specified Unicode character can be mapped to a valid OEM character.

## -parameters

### -param Char 

[in, out]
Pointer to the character. If the character can be mapped to a valid OEM character, this parameter receives the Unicode translation of the valid OEM character.

## -returns

<b>RtlIsValidOemCharacter</b> returns <b>TRUE</b> if the character can be mapped to a valid OEM character, <b>FALSE</b> otherwise.

## -remarks

<b>RtlIsValidOemCharacter</b> translates the Unicode character at <i>Char</i> using the OEM code page that was installed as the current system code page at system boot time, and converts the translated character to uppercase. <b>RtlIsValidOemCharacter</b> checks that the resulting character is a valid OEM character.

For information about other string-handling routines, see <a href="/windows-hardware/drivers/ddi/_kernel/#run-time-library-rtl-routines">Run-Time Library (RTL) Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtocountedunicodestring">RtlOemStringToCountedUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtloemstringtounicodestring">RtlOemStringToUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlunicodetooemn">RtlUnicodeToOemN</a>
