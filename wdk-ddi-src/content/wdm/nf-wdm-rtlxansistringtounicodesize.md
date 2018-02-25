---
UID: NF:wdm.RtlxAnsiStringToUnicodeSize
title: RtlxAnsiStringToUnicodeSize function
author: windows-driver-content
description: The RtlxAnsiStringToUnicodeSize routine returns the number of bytes that are required for a null-terminated Unicode string that is equivalent to a specified ANSI string.
old-location: kernel\rtlxansistringtounicodesize.htm
old-project: kernel
ms.assetid: 232ac7b0-d949-4db6-a243-b4e5ca0f3cc0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, R, RtlxAnsiStringToUnicodeSize, RtlxAnsiStringToUnicodeSize routine [Kernel-Mode Driver Architecture], S, T, U, c, d, e, g, i, k109_9343d498-bc89-428c-8e68-53c205c58bae.xml, kernel.rtlxansistringtounicodesize, l, n, o, r, s, t, wdm/RtlxAnsiStringToUnicodeSize, x, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlxAnsiStringToUnicodeSize
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlxAnsiStringToUnicodeSize function


## -description


The <b>RtlxAnsiStringToUnicodeSize</b> routine returns the number of bytes that are required for a null-terminated Unicode string that is equivalent to a specified ANSI string.


## -syntax


````
ULONG RtlxAnsiStringToUnicodeSize(
  _In_ PCANSI_STRING AnsiString
);
````


## -parameters




### -param AnsiString [in]

Pointer to the ANSI string for which to compute the number of bytes that are required for an equivalent null-terminated Unicode string. 


## -returns



<b>RtlxAnsiStringToUnicodeSize</b> returns the number of bytes that are required for an equivalent null-terminated Unicode string, if the ANSI string can be translated into an Unicode string by using the current system locale information. Otherwise, this routine returns zero.




## -remarks



The ANSI string is interpreted for the current system locale. 




## -see-also

<a href="..\wdm\nf-wdm-rtlansistringtounicodesize.md">RtlAnsiStringToUnicodeSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlxAnsiStringToUnicodeSize routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

