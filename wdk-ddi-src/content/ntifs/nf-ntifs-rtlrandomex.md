---
UID: NF:ntifs.RtlRandomEx
title: RtlRandomEx function
author: windows-driver-content
description: The RtlRandomEx routine returns a random number that was generated from a given seed value.
old-location: ifsk\rtlrandomex.htm
old-project: ifsk
ms.assetid: 2a5c70da-69dc-431c-9ce9-908633045372
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RtlRandomEx, RtlRandomEx routine [Installable File System Drivers], ifsk.rtlrandomex, ntifs/RtlRandomEx, rtlref_29425246-066b-4f0f-ba4b-419db1de119d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlRandomEx
product: Windows
targetos: Windows
req.typenames: 
---

# RtlRandomEx function


## -description


The <b>RtlRandomEx</b> routine returns a random number that was generated from a given seed value. 


## -parameters




### -param Seed [in, out]

Unsigned long value from which to generate a random number. 


## -returns



<b>RtlRandomEx</b> returns a random number in the range [0..MAXLONG-1]. 




## -remarks



<b>RtlRandomEx</b> returns values that are uniformly distributed over the range from zero to the maximum possible LONG value less 1 if it is called repeatedly with the same <i>Seed</i>.

The <b>RtlRandomEx</b> function is an improved version of the <b>RtlRandom</b> function. Compared with the <b>RtlRandom</b> function, <b>RtlRandomEx</b> is twice as fast and produces better random numbers since the period of the random numbers generated is comparatively higher. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553177">RtlRandom</a>
 

 

