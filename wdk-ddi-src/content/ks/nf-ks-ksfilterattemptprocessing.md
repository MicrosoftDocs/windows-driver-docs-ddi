---
UID: NF:ks.KsFilterAttemptProcessing
title: KsFilterAttemptProcessing function
author: windows-driver-content
description: The KsFilterAttemptProcessing function attempts to initiate processing on Filter.
old-location: stream\ksfilterattemptprocessing.htm
old-project: stream
ms.assetid: 22c6bd15-98b7-4905-8551-c8202cc6840b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsFilterAttemptProcessing function [Streaming Media Devices], ks/KsFilterAttemptProcessing, avfunc_ee888474-cf0c-4b23-b8a2-f1e7491db8fd.xml, stream.ksfilterattemptprocessing, KsFilterAttemptProcessing
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Ks.lib
-	Ks.dll
apiname: 
-	KsFilterAttemptProcessing
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterAttemptProcessing function


## -description


The<b> KsFilterAttemptProcessing</b> function attempts to initiate processing on <i>Filter</i>.


## -syntax


````
void KsFilterAttemptProcessing(
  _In_ PKSFILTER Filter,
  _In_ BOOLEAN   Asynchronous
);
````


## -parameters




### -param Filter [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure representing the AVStream filter object on which to attempt processing.


### -param Asynchronous [in]

This parameter contains an indication as to whether the processing dispatch should occur asynchronously or not (should it occur). An asynchronous dispatch is guaranteed if this is <b>TRUE</b>; however, synchronous processing dispatches are governed by conditions described below.


## -returns


None



## -remarks


If the minidriver calls <b>KsFilterAttemptProcessing</b> when all of the conditions required to process data are met, a processing dispatch occurs. For more information about the process callback, see <a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a>. In order for the attempt to result in an actual dispatch, the filter's process control gate must be in an open state. Unlike pin-centric processing, filter-centric processing has many conditions that affect the process control gate. For more information about these requirements, see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a> and <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a>.

If the process control gate is open, a processing dispatch occurs, either synchronously or asynchronously. If the caller specifies <b>TRUE</b> in the <i>Asynchronous</i> parameter, the processing dispatch always occurs asynchronously in a work item. However, if the caller requests a synchronous processing dispatch, the dispatch occurs synchronously only if the system is currently at an IRQL at which the minidriver can handle processing. If the system is at PASSIVE_LEVEL, the dispatch is guaranteed to happen synchronously. Conversely, if the system is at DISPATCH_LEVEL, the dispatch happens synchronously only if KSFILTER_FLAG_DISPATCH_LEVEL_PROCESSING is specified on the filter. Otherwise, a work item is queued to perform processing.

Note that this is only an attempt at processing; calling this function does not guarantee that processing will commence. Processing occurs only if the process control gate is "open." For more information, see <a href="https://msdn.microsoft.com/f60d4dbd-61e6-4ae2-aa43-9edc8f36c3ff">Restarting Processing in AVStream</a> and <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.



## -see-also

<a href="..\ks\nf-ks-ksgatecapturethreshold.md">KsGateCaptureThreshold</a>

<a href="..\ks\nf-ks-kspinattemptprocessing.md">KsPinAttemptProcessing</a>

<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>

<a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterAttemptProcessing function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

