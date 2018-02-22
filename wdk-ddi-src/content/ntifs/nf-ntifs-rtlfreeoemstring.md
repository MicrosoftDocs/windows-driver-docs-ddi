---
UID: NF:ntifs.RtlFreeOemString
title: RtlFreeOemString function
author: windows-driver-content
description: The RtlFreeOemString routine releases storage that was allocated by any of the Rtl..ToOemString routines.
old-location: ifsk\rtlfreeoemstring.htm
old-project: ifsk
ms.assetid: cd9bc03d-1f57-420c-9430-d2d742f654e1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlFreeOemString routine [Installable File System Drivers], rtlref_ffc98e3c-a96f-4250-a527-bcd1ba2ce506.xml, RtlFreeOemString, ifsk.rtlfreeoemstring, ntifs/RtlFreeOemString
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
-	RtlFreeOemString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlFreeOemString function


## -description


The <b>RtlFreeOemString</b> routine releases storage that was allocated by any of the <b>Rtl..ToOemString</b> routines. 


## -syntax


````
VOID RtlFreeOemString(
  _Inout_ POEM_STRING OemString
);
````


## -parameters




### -param OemString [in, out]

Pointer to the OEM string buffer that was allocated by a preceding call to <b>RtlUnicodeStringToCountedOemString</b>, <b>RtlUnicodeStringToOemString</b>, <b>RtlUpcaseUnicodeStringToCountedOemString</b>, or <b>RtlUpcaseUnicodeStringToOemString</b>. 


## -returns



None




## -remarks



<b>RtlFreeOemString</b> deallocates memory only for the buffered OEM string. This routine does not free the buffered Unicode string passed in a preceding call to the <b>Rtl..ToOemString</b> routine. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlunicodestringtocountedoemstring.md">RtlUnicodeStringToCountedOemString</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtooemstring.md">RtlUpcaseUnicodeStringToOemString</a>



<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md">RtlUnicodeStringToOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtocountedoemstring.md">RtlUpcaseUnicodeStringToCountedOemString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlFreeOemString routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

