---
UID: NF:rxtimer.RxCancelTimerRequest
title: RxCancelTimerRequest function (rxtimer.h)
description: RxCancelTimerRequest cancels a recurrent timer request. The request to be canceled is identified by the worker thread routine and associated context.
old-location: ifsk\rxcanceltimerrequest.htm
tech.root: ifsk
ms.assetid: b5aeb972-3e52-4cdc-842b-7848bb2f8dc7
ms.date: 04/16/2018
ms.keywords: RxCancelTimerRequest, RxCancelTimerRequest routine [Installable File System Drivers], ifsk.rxcanceltimerrequest, rxref_f9950992-18a5-4418-a18d-e105ecdc74ff.xml, rxtimer/RxCancelTimerRequest
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxtimer.h
api_name:
- RxCancelTimerRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCancelTimerRequest function


## -description


<b>RxCancelTimerRequest</b> cancels a recurrent timer request. The request to be canceled is identified by the worker thread routine and associated context. 


## -parameters




### -param pDeviceObject [in]

A pointer to the device object that initialized the timer. This parameter was passed to the <b>RxPostRecurrentTimerRequest</b> routine when this recurrent timer was initialized.


### -param Routine [in]

A pointer to the worker thread routine to call when this timer expires. This parameter was passed to the <b>RxPostRecurrentTimerRequest</b> routine when this recurrent timer was initialized.


### -param pContext [in]

A pointer to the context parameter that was passed to the <b>RxPostRecurrentTimerRequest</b> routine when this timer was initialized.


## -returns



<b>RxCancelTimerRequest</b> returns STATUS_SUCCESS on success. 




## -remarks



A recurrent timer is initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554615">RxPostRecurrentTimerRequest</a>.

If the recurrent timer is not found, this routine will return STATUS_NOT_FOUND.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554612">RxPostOneShotTimerRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554615">RxPostRecurrentTimerRequest</a>
 

 

