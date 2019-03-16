---
UID: NF:ntifs.RtlUpcaseUnicodeStringToCountedOemString
title: RtlUpcaseUnicodeStringToCountedOemString function (ntifs.h)
description: The RtlUpcaseUnicodeStringToCountedOemString routine translates a given Unicode source string into an uppercase counted OEM string using the current system OEM code page.
old-location: ifsk\rtlupcaseunicodestringtocountedoemstring.htm
tech.root: ifsk
ms.assetid: c1e466d7-892f-4049-a6c2-60ab8f960acb
ms.date: 04/16/2018
ms.keywords: RtlUpcaseUnicodeStringToCountedOemString, RtlUpcaseUnicodeStringToCountedOemString routine [Installable File System Drivers], ifsk.rtlupcaseunicodestringtocountedoemstring, ntifs/RtlUpcaseUnicodeStringToCountedOemString, rtlref_54925045-9df1-41ef-9878-030f30e2a0f1.xml
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlUpcaseUnicodeStringToCountedOemString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlUpcaseUnicodeStringToCountedOemString function


## -description


The <b>RtlUpcaseUnicodeStringToCountedOemString</b> routine translates a given Unicode source string into an uppercase counted OEM string using the current system OEM code page. 


## -parameters




### -param DestinationString

Pointer to a caller-allocated buffer to receive the counted OEM string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the OEM data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlUpcaseUnicodeStringToCountedOemString </b>allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the Unicode string to be translated. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlUpcaseUnicodeStringToCountedOemString </b>should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeOemString</b>. 


## -returns



<b>RtlUpcaseUnicodeStringToCountedOemString</b> returns STATUS_SUCCESS if it returns a translated string at <i>DestinationString</i>. Otherwise, no storage was allocated, nor was any conversion performed. It returns STATUS_UNMAPPABLE_CHARACTER if it cannot translate a character in the given <i>SourceString</i>. 




## -remarks



<b>RtlUpcaseUnicodeStringToCountedOemString</b> returns a string that is not null-terminated. It translates the given source string using the OEM code page that was installed as the current system code page at system boot time, and converts the translated string to uppercase. 

To find a best-match mapping for any special characters, such as a copyright character, in the given source string, <b>RtlUpcaseUnicodeStringToCountedOemString</b> performs the following operations: 

<ol>
<li>
Translates a copy of the Unicode string at <i>SourceString</i> into an OEM string

</li>
<li>
Translates the OEM string back into Unicode

</li>
<li>
Converts this new Unicode string to uppercase

</li>
<li>
Translates the uppercase Unicode string into a counted OEM string and returns it at <i>DestinationString</i>

</li>
</ol>
This routine does not modify the source string. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552281">RtlFreeOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553142">RtlOemStringToCountedUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553251">RtlUnicodeStringToCountedOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553254">RtlUnicodeStringToOemSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553282">RtlUpcaseUnicodeStringToOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553309">RtlUpcaseUnicodeToOemN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

