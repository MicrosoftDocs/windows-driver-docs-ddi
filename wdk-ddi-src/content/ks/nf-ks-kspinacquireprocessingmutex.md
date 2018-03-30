---
UID: NF:ks.KsPinAcquireProcessingMutex
title: KsPinAcquireProcessingMutex function
author: windows-driver-content
description: The KsPinAcquireProcessingMutex function acquires the processing mutex for the AVStream pin specified by Pin.
old-location: stream\kspinacquireprocessingmutex.htm
old-project: stream
ms.assetid: ce1fb470-6fee-4de0-a5db-15875a14e581
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinAcquireProcessingMutex, KsPinAcquireProcessingMutex function [Streaming Media Devices], avfunc_d06d3037-45b0-4931-86e4-ef7c586bcdf1.xml, ks/KsPinAcquireProcessingMutex, stream.kspinacquireprocessingmutex
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
-	KsPinAcquireProcessingMutex
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinAcquireProcessingMutex function


## -description


The<b> KsPinAcquireProcessingMutex </b>function acquires the processing mutex for the AVStream pin specified by <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure for which to acquire the processing mutex.


## -returns



None




## -remarks



For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563485">KsPinAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563526">KsPinReleaseControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563527">KsPinReleaseProcessingMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566780">KsReleaseControl</a>
 

 

