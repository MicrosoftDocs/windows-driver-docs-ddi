---
UID: NF:miniport.InterlockedExchangePointer
title: InterlockedExchangePointer function
author: windows-driver-content
description: The InterlockedExchangePointer routine performs an atomic operation that sets a pointer to a new value.
old-location: kernel\interlockedexchangepointer.htm
old-project: kernel
ms.assetid: 8c39a62d-0c05-4d26-b104-90c436e821cb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: InterlockedExchangePointer, InterlockedExchangePointer routine [Kernel-Mode Driver Architecture], k102_4959af35-65d8-4768-94f7-a2dad0a2db46.xml, kernel.interlockedexchangepointer, wdm/InterlockedExchangePointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	InterlockedExchangePointer
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---

# InterlockedExchangePointer function


## -description


The <b>InterlockedExchangePointer</b> routine performs an atomic operation that sets a pointer to a new value.


## -syntax


````
PVOID InterlockedExchangePointer(
  _Inout_  PVOID volatile *Target,
  _In_opt_ PVOID          Value
);
````


## -parameters




### -param Target [in, out]

A pointer to a PVOID value. The routine sets (*<i>Target</i>) to <i>Value</i>.


### -param Value [in, optional]

Specifies the PVOID value to set (*<i>Target</i>) to.


## -returns



<b>InterlockedExchangePointer</b> returns the original value of the pointer at *<i>Target</i> (that is, the value of this pointer at entry to the routine).




## -remarks



<b>InterlockedExchangePointer</b> provides a fast, atomic way to synchronize updating a pointer variable that is shared by multiple threads.

<b>InterlockedExchangePointer</b> is designed for speed and, typically, is implemented inline by a compiler. <b>InterlockedExchangePointer</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. It does not use a spin lock and can be safely used on pageable data. 

The <i>Target</i> parameter should be aligned on either a 32-bit or 64-bit boundary, depending on the system type, for better performance.

A call to <b>InterlockedExchangePointer</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls.

Interlocked operations cannot be used on non-cached memory. 




## -see-also

<a href="..\wdm\nf-wdm-interlockedexchange.md">InterlockedExchange</a>



<a href="..\wdm\nf-wdm-interlockedcompareexchange.md">InterlockedCompareExchange</a>



<a href="..\wdm\nf-wdm-interlockedcompareexchangepointer.md">InterlockedCompareExchangePointer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedExchangePointer routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

