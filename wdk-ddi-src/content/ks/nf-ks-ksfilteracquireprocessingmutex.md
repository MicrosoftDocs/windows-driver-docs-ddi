---
UID: NF:ks.KsFilterAcquireProcessingMutex
title: KsFilterAcquireProcessingMutex function
author: windows-driver-content
description: The KsFilterAcquireProcessingMutex function acquires the processing mutex for a specified AVStream filter.
old-location: stream\ksfilteracquireprocessingmutex.htm
old-project: stream
ms.assetid: d4a2fe1a-9a16-45b8-b061-9d1b1398e801
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsFilterAcquireProcessingMutex, KsFilterAcquireProcessingMutex function [Streaming Media Devices], avfunc_9c0c5db4-4bac-45a6-a61f-94bdcce07fd8.xml, ks/KsFilterAcquireProcessingMutex, stream.ksfilteracquireprocessingmutex
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsFilterAcquireProcessingMutex
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterAcquireProcessingMutex function


## -description


The<b> KsFilterAcquireProcessingMutex </b>function acquires the processing mutex for a specified AVStream filter. 


## -parameters




### -param Filter [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure representing the AVStream filter for which to acquire the processing mutex.


## -returns



None




## -remarks



AVStream holds the processing control mutex upon return from this routine. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

A minidriver that must suspend processing for a long period of time should not use this mechanism. Instead, it should manipulate the processing control gate directly by using the <b>KSGATE</b><i>Xxx</i> functions. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562527">KsFilterAttemptProcessing</a>



<b>KsFilterReleaseProcessingMutex</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563488">KsPinAcquireProcessingMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563502">KsPinGetAndGate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563527">KsPinReleaseProcessingMutex</a>
 

 

