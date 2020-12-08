---
UID: NF:rxworkq.RxSpinDownMRxDispatcher
title: RxSpinDownMRxDispatcher function (rxworkq.h)
description: RxSpinDownMRxDispatcher tears down the dispatcher context for a network mini-redirector.
old-location: ifsk\rxspindownmrxdispatcher.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxSpinDownMRxDispatcher function"]
ms.keywords: RxSpinDownMRxDispatcher, RxSpinDownMRxDispatcher function [Installable File System Drivers], ifsk.rxspindownmrxdispatcher, rxref_aa43a136-8df7-45f1-bf52-48792c094f31.xml, rxworkq/RxSpinDownMRxDispatcher
req.header: rxworkq.h
req.include-header: Rxworkq.h, Rxstruc.h
req.target-type: Desktop
req.target-min-winverclnt: The RxSpinDownMRxDispatcher routine is only available on Windows XP and later.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RxSpinDownMRxDispatcher
 - rxworkq/RxSpinDownMRxDispatcher
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxworkq.h
api_name:
 - RxSpinDownMRxDispatcher
---

# RxSpinDownMRxDispatcher function


## -description

<b>RxSpinDownMRxDispatcher</b> tears down the dispatcher context for a network mini-redirector.

## -parameters

### -param pMRxDeviceObject 

[in, out]
A pointer to the device object of the corresponding network mini-redirector driver.

## -returns

<b>RxSpinDownMRxDispatcher</b> returns STATUS_SUCCESS on success. On checked builds, this routine causes the system to ASSERT on failure.

## -remarks

The <b>RxSpinDownMRxDispatcher</b> routine will set a tear down request into the driver device object of the network mini-redirector driver (the <b>DispatcherContext.pTearDownEvent</b> member of the device object is set to <b>&TearDownEvent</b>) and wait for the driver to tear down any outstanding worker threads. 

The <b>RxSpinDownMRxDispatcher</b> routine is also called internally by the <b>RxStopMiniRdr</b> and <b>RxpUnregisterMinirdr</b> routines.

## -see-also

<a href="/windows-hardware/drivers/ddi/rxworkq/nf-rxworkq-rxdispatchtoworkerthread">RxDispatchToWorkerThread</a>



<a href="/windows-hardware/drivers/ddi/rxworkq/nf-rxworkq-rxposttoworkerthread">RxPostToWorkerThread</a>
