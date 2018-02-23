---
UID: NF:ntifs.RtlOemStringToUnicodeSize
title: RtlOemStringToUnicodeSize macro
author: windows-driver-content
description: The RtlOemStringToUnicodeSize routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string.
old-location: ifsk\rtloemstringtounicodesize.htm
old-project: ifsk
ms.assetid: e54d0e3f-4e46-43b5-8338-b6e2f2a14c56
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlOemStringToUnicodeSize, RtlOemStringToUnicodeSize routine [Installable File System Drivers], ifsk.rtloemstringtounicodesize, ntifs/RtlOemStringToUnicodeSize, rtlref_5f048569-d84e-43ee-8d51-1281f18c7ddf.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
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
-	RtlOemStringToUnicodeSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlOemStringToUnicodeSize macro


## -description


The <b>RtlOemStringToUnicodeSize</b> routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string. 


## -syntax


````
ULONG RtlOemStringToUnicodeSize(
  _In_ POEM_STRING OemString
);
````


## -parameters




### -param STRING

TBD






#### - OemString [in]

Pointer to a caller-allocated OEM string. 


## -remarks



<b>RtlOemStringToUnicodeSize</b> can be called to determine how much memory to allocate when translating an OEM string to Unicode with <b>RtlOemStringToUnicodeString</b>. The returned value includes space for the NULL terminator. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodesize.md">RtlOemStringToCountedUnicodeSize</a>



<a href="..\ntifs\nf-ntifs-rtloemstringtounicodestring.md">RtlOemStringToUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlOemStringToUnicodeSize routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

