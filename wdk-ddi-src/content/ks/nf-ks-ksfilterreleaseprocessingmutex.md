---
UID: NF:ks.KsFilterReleaseProcessingMutex
title: KsFilterReleaseProcessingMutex function (ks.h)
description: The KsFilterReleaseProcessingMutex function releases the processing mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilterreleaseprocessingmutex.htm
tech.root: stream
ms.assetid: 8ccf24a4-f087-4d61-8a9e-4bc05d7ec7bf
ms.date: 04/23/2018
ms.keywords: KsFilterReleaseProcessingMutex, KsFilterReleaseProcessingMutex function [Streaming Media Devices], avfunc_35026563-e7aa-4305-a4fc-2558c1b21aa7.xml, ks/KsFilterReleaseProcessingMutex, stream.ksfilterreleaseprocessingmutex
f1_keywords:
 - "ks/KsFilterReleaseProcessingMutex"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsFilterReleaseProcessingMutex
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterReleaseProcessingMutex function


## -description


The<b> KsFilterReleaseProcessingMutex </b>function releases the processing mutex for the AVStream filter specified by <i>Filter</i>.


## -parameters




### -param Filter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure representing the AVStream filter for which to release the processing mutex.


## -remarks



For more AVStream-specific information about mutexes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/processing-mutex-in-avstream">Processing Mutex in AVStream</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteracquireprocessingmutex">KsFilterAcquireProcessingMutex</a>
 

 

