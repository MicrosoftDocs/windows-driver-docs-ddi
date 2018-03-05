---
UID: NF:wdm.InterlockedExchangeAdd
title: InterlockedExchangeAdd function
author: windows-driver-content
description: The InterlockedExchangeAdd routine adds a value to a given integer as an atomic operation and returns the original value of the given integer.
old-location: kernel\interlockedexchangeadd.htm
old-project: kernel
ms.assetid: f61878b4-6bfa-463e-9fb1-c95171ce65b4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: InterlockedExchangeAdd, InterlockedExchangeAdd routine [Kernel-Mode Driver Architecture], k102_ed690604-0379-476d-b838-4820f47b850a.xml, kernel.interlockedexchangeadd, wdm/InterlockedExchangeAdd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.lib: OneCoreUAP.lib on Windows 10
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	OneCoreUAP.lib
-	OneCoreUAP.dll
-	API-MS-Win-Core-Interlocked-l1-1-0.dll
-	API-MS-Win-Core-Interlocked-l1-2-0.dll
-	KernelBase.dll
-	MinKernelBase.dll
api_name:
-	InterlockedExchangeAdd
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# InterlockedExchangeAdd function


## -description


The <b>InterlockedExchangeAdd</b> routine adds a value to a given integer as an atomic operation and returns the original value of the given integer.


## -syntax


````
LONG InterlockedExchangeAdd(
  _Inout_ LONG volatile *Addend,
  _In_    LONG          Value
);
````


## -parameters




### -param Addend [in, out]

A pointer to an integer variable.


### -param Value [in]

Specifies the value to be added to <i>Addend</i>. 


## -returns



<b>InterlockedExchangeAdd</b> returns the original value of the <i>Addend</i> variable when the call occurred.




## -remarks



<b>InterlockedExchangeAdd</b> should be used instead of <b>ExInterlockedAddUlong</b> because it is both faster and more efficient. 

<b>InterlockedExchangeAdd</b> is implemented inline by the compiler when appropriate and possible. It does not require a spin lock and can therefore be safely used on pageable data.

<b>InterlockedExchangeAdd</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. 

Interlocked operations cannot be used on non-cached memory. 




## -see-also

<a href="..\wdm\nf-wdm-exinterlockedaddulong.md">ExInterlockedAddUlong</a>



<a href="..\wdm\nf-wdm-interlockeddecrement.md">InterlockedDecrement</a>



<a href="..\wdm\nf-wdm-interlockedincrement.md">InterlockedIncrement</a>



<a href="..\wdm\nf-wdm-exinterlockedaddlargeinteger.md">ExInterlockedAddLargeInteger</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedExchangeAdd routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

