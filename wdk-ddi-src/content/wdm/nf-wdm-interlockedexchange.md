---
UID: NF:wdm.InterlockedExchange
title: InterlockedExchange function
author: windows-driver-content
description: The InterlockedExchange routine sets an integer variable to a given value as an atomic operation.
old-location: kernel\interlockedexchange.htm
old-project: kernel
ms.assetid: c9bee5b0-eeaf-4c82-9f02-d00cf9202f78
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k102_ae8d85b7-040e-4c44-9476-68d6919a50e4.xml, InterlockedExchange, InterlockedExchange routine [Kernel-Mode Driver Architecture], kernel.interlockedexchange, wdm/InterlockedExchange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	OneCoreUAP.lib
-	OneCoreUAP.dll
-	API-MS-Win-Core-Interlocked-l1-1-0.dll
-	API-MS-Win-Core-Interlocked-l1-2-0.dll
-	KernelBase.dll
-	MinKernelBase.dll
apiname:
-	InterlockedExchange
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# InterlockedExchange function


## -description


The <b>InterlockedExchange</b> routine sets an integer variable to a given value as an atomic operation.


## -syntax


````
LONG InterlockedExchange(
  _Inout_ LONG volatile *Target,
  _In_    LONG          Value
);
````


## -parameters




### -param Target [in, out]

A pointer to a variable to be set to the supplied <i>Value</i> as an atomic operation.


### -param Value [in]

Specifies the value to which the variable will be set. 


## -returns



<b>InterlockedExchange</b> returns the value of the variable at <i>Target</i> when the call occurred.




## -remarks



<b>InterlockedExchange</b> should be used instead of <b>ExInterlockedExchangeUlong</b>, because it is both faster and more efficient. 

<b>InterlockedExchange</b> is implemented inline by the compiler when appropriate and possible. It does not require a spin lock and can therefore be safely used on pageable data.

A call to <b>InterlockedExchange</b> routine is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. 

Interlocked operations cannot be used on non-cached memory. 




## -see-also

<a href="..\wdm\nf-wdm-exinterlockedaddulong.md">ExInterlockedAddUlong</a>



<a href="..\wdm\nf-wdm-exinterlockedaddlargeinteger.md">ExInterlockedAddLargeInteger</a>



<a href="..\wdm\nf-wdm-interlockeddecrement.md">InterlockedDecrement</a>



<a href="..\wdm\nf-wdm-interlockedincrement.md">InterlockedIncrement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedExchange routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

