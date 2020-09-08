---
UID: NF:ks.KsFilterAcquireProcessingMutex
title: KsFilterAcquireProcessingMutex function (ks.h)
description: The KsFilterAcquireProcessingMutex function acquires the processing mutex for a specified AVStream filter.
old-location: stream\ksfilteracquireprocessingmutex.htm
tech.root: stream
ms.assetid: d4a2fe1a-9a16-45b8-b061-9d1b1398e801
ms.date: 04/23/2018
keywords: ["KsFilterAcquireProcessingMutex function"]
ms.keywords: KsFilterAcquireProcessingMutex, KsFilterAcquireProcessingMutex function [Streaming Media Devices], avfunc_9c0c5db4-4bac-45a6-a61f-94bdcce07fd8.xml, ks/KsFilterAcquireProcessingMutex, stream.ksfilteracquireprocessingmutex
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterAcquireProcessingMutex
 - ks/KsFilterAcquireProcessingMutex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterAcquireProcessingMutex
---

# KsFilterAcquireProcessingMutex function


## -description

The<b> KsFilterAcquireProcessingMutex </b>function acquires the processing mutex for a specified AVStream filter.

## -parameters

### -param Filter 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure representing the AVStream filter for which to acquire the processing mutex.

## -remarks

AVStream holds the processing control mutex upon return from this routine. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

A minidriver that must suspend processing for a long period of time should not use this mechanism. Instead, it should manipulate the processing control gate directly by using the <b>KSGATE</b><i>Xxx</i> functions.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterattemptprocessing">KsFilterAttemptProcessing</a>



<b>KsFilterReleaseProcessingMutex</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinacquireprocessingmutex">KsPinAcquireProcessingMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetandgate">KsPinGetAndGate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinreleaseprocessingmutex">KsPinReleaseProcessingMutex</a>

