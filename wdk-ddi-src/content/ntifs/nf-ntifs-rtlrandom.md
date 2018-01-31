---
UID: NF:ntifs.RtlRandom
title: RtlRandom function
author: windows-driver-content
description: The RtlRandom routine returns a random number that was generated from a given seed value.
old-location: ifsk\rtlrandom.htm
old-project: ifsk
ms.assetid: f3975ad7-8eb8-4f46-8024-6a1decc21c77
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/RtlRandom, rtlref_c9c196b4-7335-4320-ae7f-7c565b6f73e6.xml, ifsk.rtlrandom, RtlRandom routine [Installable File System Drivers], RtlRandom
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
-	RtlRandom
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlRandom function


## -description


The <b>RtlRandom</b> routine returns a random number that was generated from a given seed value. 


## -syntax


````
ULONG RtlRandom(
  _Inout_ PULONG Seed
);
````


## -parameters




#### - Seed [in, out]

Unsigned long value from which to generate a random number. 


## -returns


<b>RtlRandom</b> returns a random number in the range [0..MAXLONG-1]. 



## -remarks


<b>RtlRandom</b> returns values that are uniformly distributed over the range from zero to the maximum possible LONG value less 1 if it is called repeatedly with the same <i>Seed</i>.

The <b>RtlRandomEx</b> function is an improved version of the <b>RtlRandom</b> function that is twice as fast and produces better random numbers. 



## -see-also

<a href="..\ntifs\nf-ntifs-rtlrandomex.md">RtlRandomEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlRandom routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

