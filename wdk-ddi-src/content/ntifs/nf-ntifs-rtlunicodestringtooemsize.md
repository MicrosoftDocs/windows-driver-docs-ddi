---
UID: NF:ntifs.RtlUnicodeStringToOemSize
title: RtlUnicodeStringToOemSize macro
author: windows-driver-content
description: The RtlUnicodeStringToOemSize routine determines the size, in bytes, that a given Unicode string will be after it is translated into an OEM string.
old-location: ifsk\rtlunicodestringtooemsize.htm
old-project: ifsk
ms.assetid: 0e648c99-6d1a-4515-af17-a16e88351f45
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , O, R, RtlUnicodeStringToOemSize, RtlUnicodeStringToOemSize routine [Installable File System Drivers], S, T, U, c, d, e, g, i, ifsk.rtlunicodestringtooemsize, l, m, n, ntifs/RtlUnicodeStringToOemSize, o, r, rtlref_836e23f0-2e1a-474e-a66c-615f260e2f4f.xml, t, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	RtlUnicodeStringToOemSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlUnicodeStringToOemSize macro


## -description


The <b>RtlUnicodeStringToOemSize</b> routine determines the size, in bytes, that a given Unicode string will be after it is translated into an OEM string. 


## -syntax


````
ULONG RtlUnicodeStringToOemSize(
  _In_ PUNICODE_STRING UnicodeString
);
````


## -parameters




### -param STRING

TBD






#### - UnicodeString [in]

Pointer to a caller-allocated Unicode string. 


## -remarks



<b>RtlUnicodeStringToOemSize</b> can be called to determine how much memory to allocate when translating a Unicode string to OEM characters with <b>RtlUnicodeStringToOemString</b> or <b>RtlUpcaseUnicodeStringToOemString</b>. The returned value includes space for a NULL terminator for the OEM string. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtloemstringtounicodesize.md">RtlOemStringToUnicodeSize</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtooemstring.md">RtlUpcaseUnicodeStringToOemString</a>



<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md">RtlUnicodeStringToOemString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUnicodeStringToOemSize routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

