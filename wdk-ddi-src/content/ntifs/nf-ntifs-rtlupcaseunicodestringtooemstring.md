---
UID: NF:ntifs.RtlUpcaseUnicodeStringToOemString
title: RtlUpcaseUnicodeStringToOemString function
author: windows-driver-content
description: The RtlUpcaseUnicodeStringToOemString routine translates a given Unicode source string into an uppercase OEM string using the current system OEM code page.
old-location: ifsk\rtlupcaseunicodestringtooemstring.htm
old-project: ifsk
ms.assetid: 3d81c5e4-780b-4b1f-ad3a-6d59cab5650f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlUpcaseUnicodeStringToOemString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlUpcaseUnicodeStringToOemString
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# RtlUpcaseUnicodeStringToOemString function



## -description
The <b>RtlUpcaseUnicodeStringToOemString</b> routine translates a given Unicode source string into an uppercase OEM string using the current system OEM code page. 



## -syntax

````
NTSTATUS RtlUpcaseUnicodeStringToOemString(
       POEM_STRING      DestinationString,
  _In_ PCUNICODE_STRING SourceString,
  _In_ BOOLEAN          AllocateDestinationString
);
````


## -parameters

### -param DestinationString 

Pointer to a caller-allocated buffer to receive the counted OEM string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the OEM data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlUpcaseUnicodeStringToOemString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the Unicode string to be translated. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlUpcaseUnicodeStringToOemString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeOemString</b>. 


## -returns
<b>RtlUpcaseUnicodeStringToOemString</b> returns STATUS_SUCCESS if the string at <i>DestinationString</i> is translated. Otherwise, no storage was allocated, nor was any conversion performed. 


## -remarks
<b>RtlUpcaseUnicodeStringToOemString</b> translates the given source string using the OEM code page that was installed as the current system code page at system boot time, and converts the OEM string to uppercase. 

This routine can substitute a default character in the destination string for all source string characters that it cannot map to the current code page and, then, return STATUS_SUCCESS. 

This routine does not modify the source string. It returns a null-terminated OEM string. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlfreeoemstring.md">RtlFreeOemString</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlunicodestringtocountedoemstring.md">RtlUnicodeStringToCountedOemString</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md">RtlUnicodeStringToOemString</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemsize.md">RtlUnicodeStringToOemSize</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlupcaseunicodetooemn.md">RtlUpcaseUnicodeToOemN</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUpcaseUnicodeStringToOemString routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

