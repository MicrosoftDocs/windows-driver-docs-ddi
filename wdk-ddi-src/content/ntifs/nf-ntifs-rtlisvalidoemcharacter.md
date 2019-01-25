---
UID: NF:ntifs.RtlIsValidOemCharacter
title: RtlIsValidOemCharacter function (ntifs.h)
description: The RtlIsValidOemCharacter routine determines if the specified Unicode character can be mapped to a valid OEM character.
old-location: ifsk\rtlisvalidoemcharacter.htm
tech.root: ifsk
ms.assetid: 76040e0d-a43c-4e3d-aaaa-b84fc2613603
ms.date: 04/16/2018
ms.keywords: RtlIsValidOemCharacter, RtlIsValidOemCharacter routine [Installable File System Drivers], ifsk.rtlisvalidoemcharacter, ntifs/RtlIsValidOemCharacter, rtlref_ebbaa5fc-63da-4eef-b8ac-be10a6e062a0.xml
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlIsValidOemCharacter
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIsValidOemCharacter function


## -description


The <b>RtlIsValidOemCharacter</b> routine determines if the specified Unicode character can be mapped to a valid OEM character. 


## -parameters




### -param Char [in, out]

Pointer to the character. If the character can be mapped to a valid OEM character, this parameter receives the Unicode translation of the valid OEM character.


## -returns



<b>RtlIsValidOemCharacter</b> returns <b>TRUE</b> if the character can be mapped to a valid OEM character, <b>FALSE</b> otherwise. 




## -remarks



<b>RtlIsValidOemCharacter</b> translates the Unicode character at <i>Char</i> using the OEM code page that was installed as the current system code page at system boot time, and converts the translated character to uppercase. <b>RtlIsValidOemCharacter</b> checks that the resulting character is a valid OEM character.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553142">RtlOemStringToCountedUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553153">RtlOemStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553272">RtlUnicodeToOemN</a>
 

 

