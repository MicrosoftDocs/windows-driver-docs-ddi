---
UID: NF:ks.KsPinAcquireProcessingMutex
title: KsPinAcquireProcessingMutex function (ks.h)
description: The KsPinAcquireProcessingMutex function acquires the processing mutex for the AVStream pin specified by Pin.
old-location: stream\kspinacquireprocessingmutex.htm
tech.root: stream
ms.assetid: ce1fb470-6fee-4de0-a5db-15875a14e581
ms.date: 04/23/2018
ms.keywords: KsPinAcquireProcessingMutex, KsPinAcquireProcessingMutex function [Streaming Media Devices], avfunc_d06d3037-45b0-4931-86e4-ef7c586bcdf1.xml, ks/KsPinAcquireProcessingMutex, stream.kspinacquireprocessingmutex
ms.topic: function
f1_keywords:
 - "ks/KsPinAcquireProcessingMutex"
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
- KsPinAcquireProcessingMutex
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinAcquireProcessingMutex function


## -description


The<b> KsPinAcquireProcessingMutex </b>function acquires the processing mutex for the AVStream pin specified by <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure for which to acquire the processing mutex.


## -returns



None




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinacquirecontrol">KsPinAcquireControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinreleasecontrol">KsPinReleaseControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinreleaseprocessingmutex">KsPinReleaseProcessingMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksreleasecontrol">KsReleaseControl</a>
 

 

