---
UID: NF:ks.KsFilterReleaseProcessingMutex
title: KsFilterReleaseProcessingMutex function
description: The KsFilterReleaseProcessingMutex function releases the processing mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilterreleaseprocessingmutex.htm
tech.root: stream
ms.assetid: 8ccf24a4-f087-4d61-8a9e-4bc05d7ec7bf
ms.date: 04/23/2018
ms.keywords: KsFilterReleaseProcessingMutex, KsFilterReleaseProcessingMutex function [Streaming Media Devices], avfunc_35026563-e7aa-4305-a4fc-2558c1b21aa7.xml, ks/KsFilterReleaseProcessingMutex, stream.ksfilterreleaseprocessingmutex
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
-	KsFilterReleaseProcessingMutex
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

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure representing the AVStream filter for which to release the processing mutex.


## -returns



None




## -remarks



For more AVStream-specific information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a> and <a href="https://msdn.microsoft.com/dd84fe3f-352e-4641-99d7-792ccecb0b40">Processing Mutex in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562524">KsFilterAcquireProcessingMutex</a>
 

 

