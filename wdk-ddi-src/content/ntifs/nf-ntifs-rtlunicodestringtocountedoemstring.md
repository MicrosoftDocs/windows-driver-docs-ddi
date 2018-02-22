---
UID: NF:ntifs.RtlUnicodeStringToCountedOemString
title: RtlUnicodeStringToCountedOemString function
author: windows-driver-content
description: The RtlUnicodeStringToCountedOemString routine translates the specified Unicode source string into a counted OEM string using the current system OEM code page.
old-location: ifsk\rtlunicodestringtocountedoemstring.htm
old-project: ifsk
ms.assetid: 7479d5d0-69d0-42b8-9aa1-5eab8b71b118
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlUnicodeStringToCountedOemString routine [Installable File System Drivers], ntifs/RtlUnicodeStringToCountedOemString, ifsk.rtlunicodestringtocountedoemstring, RtlUnicodeStringToCountedOemString, rtlref_dbc62228-043f-43f1-bd19-464adf37b693.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlUnicodeStringToCountedOemString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlUnicodeStringToCountedOemString function


## -description


The <b>RtlUnicodeStringToCountedOemString</b> routine translates the specified Unicode source string into a counted OEM string using the current system OEM code page. 


## -syntax


````
NTSTATUS RtlUnicodeStringToCountedOemString(
       POEM_STRING      DestinationString,
  _In_ PCUNICODE_STRING SourceString,
  _In_ BOOLEAN          AllocateDestinationString
);
````


## -parameters




### -param DestinationString

Pointer to a caller-allocated buffer to receive the counted OEM string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the OEM data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlUnicodeStringToCountedOemString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the source Unicode string to be translated. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlUnicodeStringToCountedOemString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeOemString</b>. 


## -returns



<b>RtlUnicodeStringToCountedOemString</b> returns STATUS_SUCCESS if the string at <i>DestinationString</i> is translated. Otherwise, no storage was allocated, and no conversion was performed. This routine returns STATUS_UNMAPPABLE_CHARACTER if it cannot translate a character in the given <i>SourceString</i>.




## -remarks



<b>RtlUnicodeStringToCountedOemString</b> returns a translated string that does not include a NULL terminator. It translates the given source string using the OEM code page that was installed as the current system code page at system boot time. 

<b>RtlUnicodeStringToCountedOemString</b> does not modify the source string.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md">RtlUnicodeStringToOemString</a>



<a href="..\ntifs\nf-ntifs-rtlfreeoemstring.md">RtlFreeOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodestring.md">RtlOemStringToCountedUnicodeString</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtocountedoemstring.md">RtlUpcaseUnicodeStringToCountedOemString</a>



<a href="..\ntifs\nf-ntifs-rtlunicodetooemn.md">RtlUnicodeToOemN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUnicodeStringToCountedOemString routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

