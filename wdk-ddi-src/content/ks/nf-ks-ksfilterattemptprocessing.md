---
UID: NF:ks.KsFilterAttemptProcessing
title: KsFilterAttemptProcessing function (ks.h)
description: The KsFilterAttemptProcessing function attempts to initiate processing on Filter.
old-location: stream\ksfilterattemptprocessing.htm
tech.root: stream
ms.assetid: 22c6bd15-98b7-4905-8551-c8202cc6840b
ms.date: 04/23/2018
ms.keywords: KsFilterAttemptProcessing, KsFilterAttemptProcessing function [Streaming Media Devices], avfunc_ee888474-cf0c-4b23-b8a2-f1e7491db8fd.xml, ks/KsFilterAttemptProcessing, stream.ksfilterattemptprocessing
f1_keywords:
 - "ks/KsFilterAttemptProcessing"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsFilterAttemptProcessing
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterAttemptProcessing function


## -description


The<b> KsFilterAttemptProcessing</b> function attempts to initiate processing on <i>Filter</i>.


## -parameters




### -param Filter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure representing the AVStream filter object on which to attempt processing.


### -param Asynchronous [in]

This parameter contains an indication as to whether the processing dispatch should occur asynchronously or not (should it occur). An asynchronous dispatch is guaranteed if this is <b>TRUE</b>; however, synchronous processing dispatches are governed by conditions described below.


## -remarks



If the minidriver calls <b>KsFilterAttemptProcessing</b> when all of the conditions required to process data are met, a processing dispatch occurs. For more information about the process callback, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch">KSFILTER_DISPATCH</a>. In order for the attempt to result in an actual dispatch, the filter's process control gate must be in an open state. Unlike pin-centric processing, filter-centric processing has many conditions that affect the process control gate. For more information about these requirements, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/pin-centric-processing">Pin-Centric Processing</a>.

If the process control gate is open, a processing dispatch occurs, either synchronously or asynchronously. If the caller specifies <b>TRUE</b> in the <i>Asynchronous</i> parameter, the processing dispatch always occurs asynchronously in a work item. However, if the caller requests a synchronous processing dispatch, the dispatch occurs synchronously only if the system is currently at an IRQL at which the minidriver can handle processing. If the system is at PASSIVE_LEVEL, the dispatch is guaranteed to happen synchronously. Conversely, if the system is at DISPATCH_LEVEL, the dispatch happens synchronously only if KSFILTER_FLAG_DISPATCH_LEVEL_PROCESSING is specified on the filter. Otherwise, a work item is queued to perform processing.

Note that this is only an attempt at processing; calling this function does not guarantee that processing will commence. Processing occurs only if the process control gate is "open." For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/restarting-processing-in-avstream">Restarting Processing in AVStream</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch">KSFILTER_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgatecapturethreshold">KsGateCaptureThreshold</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinattemptprocessing">KsPinAttemptProcessing</a>
 

 

