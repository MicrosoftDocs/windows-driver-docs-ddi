---
UID: NF:rxtimer.RxPostRecurrentTimerRequest
title: RxPostRecurrentTimerRequest function
author: windows-driver-content
description: RxPostRecurrentTimerRequest initializes a recurrent timer request. The passed in pointer to a worker thread routine is called at regular intervals when the recurrent timer fires based on the input parameters to this routine.
old-location: ifsk\rxpostrecurrenttimerrequest.htm
old-project: ifsk
ms.assetid: a44fb478-4f78-415e-b557-bf383199578c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxPostRecurrentTimerRequest, RxPostRecurrentTimerRequest routine [Installable File System Drivers], ifsk.rxpostrecurrenttimerrequest, rxref_64318843-28af-4351-9273-06061b94578f.xml, rxtimer/RxPostRecurrentTimerRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxtimer.h
req.include-header: Rxtimer.h, Rxworkq.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxtimer.h
api_name:
-	RxPostRecurrentTimerRequest
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxPostRecurrentTimerRequest function


## -description


<b>RxPostRecurrentTimerRequest</b> initializes a recurrent timer request. The passed in pointer to a worker thread routine is called at regular intervals when the recurrent timer fires based on the input parameters to this routine. 


## -parameters




### -param pDeviceObject [in]

A pointer to the device object to be associated with this timer. 


### -param Routine [in]

A pointer to the worker thread routine to call when this timer expires. 


### -param pContext [in]

A pointer to the context parameter to be associated with this timer.


### -param TimeInterval [in]

The time interval, in 100-nanosecond ticks.


## -returns



<b>RxPostRecurrentTimerRequest</b> returns STATUS_SUCCESS on success or one of the following error codes: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation of non-paged pool memory required by this routine failed. 

</td>
</tr>
</table>
 




## -remarks



A recurrent timer can be canceled by calling <b>RxCancelTimerRequest</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553395">RxCancelTimerRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554612">RxPostOneShotTimerRequest</a>
 

 

