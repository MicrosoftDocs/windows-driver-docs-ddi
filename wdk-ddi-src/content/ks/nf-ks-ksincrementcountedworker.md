---
UID: NF:ks.KsIncrementCountedWorker
title: KsIncrementCountedWorker function
author: windows-driver-content
description: Increments the current worker count, and optionally queues the counted work item with the worker previously created by KsRegisterCountedWorker.
old-location: stream\ksincrementcountedworker.htm
tech.root: stream
ms.assetid: 282ffc00-ca62-4729-afe3-c13ea8069a18
ms.date: 04/23/2018
ms.keywords: KsIncrementCountedWorker, KsIncrementCountedWorker function [Streaming Media Devices], ks/KsIncrementCountedWorker, ksfunc_14b63f3e-f634-4147-891b-111179462966.xml, stream.ksincrementcountedworker
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
-	KsIncrementCountedWorker
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsIncrementCountedWorker function


## -description


Increments the current worker count, and optionally queues the counted work item with the worker previously created by <a href="https://msdn.microsoft.com/library/windows/hardware/ff566770">KsRegisterCountedWorker</a>.


## -parameters




### -param Worker [in]

Contains the previously allocated worker.


## -returns



Returns the current counter. A count of one implies that a worker was actually scheduled.




## -remarks



This should be called after an addition has been made to the worker's list of tasks to perform. A corresponding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff561660">KsDecrementCountedWorker</a> should be made within the work item after each task has been completed. This may be called at DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561660">KsDecrementCountedWorker</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566770">KsRegisterCountedWorker</a>
 

 

