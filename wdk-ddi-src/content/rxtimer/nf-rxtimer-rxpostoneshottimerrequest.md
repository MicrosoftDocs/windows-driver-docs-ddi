---
UID: NF:rxtimer.RxPostOneShotTimerRequest
title: RxPostOneShotTimerRequest function (rxtimer.h)
description: RxPostOneShotTimerRequest initializes a one-shot timer entry. The passed-in pointer to a worker thread routine is called once when the timer expires.
old-location: ifsk\rxpostoneshottimerrequest.htm
tech.root: ifsk
ms.assetid: d3ae6401-6d1b-428f-ae74-e262682bcb10
ms.date: 04/16/2018
keywords: ["RxPostOneShotTimerRequest function"]
ms.keywords: RxPostOneShotTimerRequest, RxPostOneShotTimerRequest routine [Installable File System Drivers], ifsk.rxpostoneshottimerrequest, rxref_9fb32d67-ac0a-4f85-b999-5f5beaf6b26f.xml, rxtimer/RxPostOneShotTimerRequest
f1_keywords:
 - "rxtimer/RxPostOneShotTimerRequest"
 - "RxPostOneShotTimerRequest"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxtimer.h
api_name:
- RxPostOneShotTimerRequest
targetos: Windows
req.typenames: 
---

# RxPostOneShotTimerRequest function


## -description


<b>RxPostOneShotTimerRequest</b> initializes a one-shot timer entry. The passed-in pointer to a worker thread routine is called once when the timer expires. 


## -parameters




### -param pDeviceObject [in]

A pointer to the device object to be associated with this timer. 


### -param pWorkItem [in]

A pointer to the worker item.


### -param Routine [in]

A pointer to the worker thread routine to call when this timer expires. 


### -param pContext [in]

A pointer to the context parameter associated with this timer.


### -param TimeInterval [in]

The time interval, in 100-nanosecond ticks.


## -returns



<b>RxPostOneShotTimerRequest</b>
      returns STATUS_SUCCESS on success. 

If a <b>NULL</b> pointer is passed as the <i>pWorkItem</i> parameter, this routine causes the system to ASSERT on checked builds.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxtimer/nf-rxtimer-rxcanceltimerrequest">RxCancelTimerRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxtimer/nf-rxtimer-rxpostrecurrenttimerrequest">RxPostRecurrentTimerRequest</a>
 

 

