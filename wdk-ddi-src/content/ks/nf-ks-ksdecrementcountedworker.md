---
UID: NF:ks.KsDecrementCountedWorker
title: KsDecrementCountedWorker function
description: Decrements the current worker count of a worker previous created by KsRegisterCountedWorker. This should be called after each task within a worker has been completed.
old-location: stream\ksdecrementcountedworker.htm
tech.root: stream
ms.assetid: 2b38e4df-e5b6-480b-bd4e-62e059e26411
ms.date: 04/23/2018
ms.keywords: KsDecrementCountedWorker, KsDecrementCountedWorker function [Streaming Media Devices], ks/KsDecrementCountedWorker, ksfunc_7ddba520-3deb-4160-87e1-a12d2210b5da.xml, stream.ksdecrementcountedworker
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsDecrementCountedWorker
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDecrementCountedWorker function


## -description


Decrements the current worker count of a worker previous created by <a href="https://msdn.microsoft.com/library/windows/hardware/ff566770">KsRegisterCountedWorker</a>. This should be called after each task within a worker has been completed. 


## -parameters




### -param Worker [in]

Contains the previously allocated worker.


## -returns



Returns the current counter. A count of zero implies that the task list has been completed.




## -remarks



<b>KsDecrementCountedWorker</b> should be called after each task within a worker has been completed. A corresponding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562678">KsIncrementCountedWorker</a> would have previously incremented the count. <b>KsDecrementCountedWorker</b> may be called at DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562678">KsIncrementCountedWorker</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566770">KsRegisterCountedWorker</a>
 

 

