---
UID: NF:ks.KsIncrementCountedWorker
title: KsIncrementCountedWorker function
author: windows-driver-content
description: Increments the current worker count, and optionally queues the counted work item with the worker previously created by KsRegisterCountedWorker.
old-location: stream\ksincrementcountedworker.htm
old-project: stream
ms.assetid: 282ffc00-ca62-4729-afe3-c13ea8069a18
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsIncrementCountedWorker, KsIncrementCountedWorker function [Streaming Media Devices], ks/KsIncrementCountedWorker, stream.ksincrementcountedworker, ksfunc_14b63f3e-f634-4147-891b-111179462966.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsIncrementCountedWorker
product: Windows
targetos: Windows
req.typenames: 
---

# KsIncrementCountedWorker function


## -description


Increments the current worker count, and optionally queues the counted work item with the worker previously created by <a href="..\ks\nf-ks-ksregistercountedworker.md">KsRegisterCountedWorker</a>.


## -syntax


````
ULONG KsIncrementCountedWorker(
  _In_ PKSWORKER Worker
);
````


## -parameters




### -param Worker [in]

Contains the previously allocated worker.


## -returns



Returns the current counter. A count of one implies that a worker was actually scheduled.




## -remarks



This should be called after an addition has been made to the worker's list of tasks to perform. A corresponding call to <a href="..\ks\nf-ks-ksdecrementcountedworker.md">KsDecrementCountedWorker</a> should be made within the work item after each task has been completed. This may be called at DISPATCH_LEVEL.




## -see-also

<a href="..\ks\nf-ks-ksregistercountedworker.md">KsRegisterCountedWorker</a>



<a href="..\ks\nf-ks-ksdecrementcountedworker.md">KsDecrementCountedWorker</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsIncrementCountedWorker function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

