---
UID: NF:ks.KsUnregisterWorker
title: KsUnregisterWorker function
description: The KsUnregisterWorker function allows clients to unregister a worker.
old-location: stream\ksunregisterworker.htm
tech.root: stream
ms.assetid: 789b12db-7f51-426f-8f43-d3a3e43d85b3
ms.date: 04/23/2018
ms.keywords: KsUnregisterWorker, KsUnregisterWorker function [Streaming Media Devices], ks/KsUnregisterWorker, ksfunc_9b3f2185-8ab0-484d-91d7-3b822ce1c4aa.xml, stream.ksunregisterworker
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
-	KsUnregisterWorker
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsUnregisterWorker function


## -description


The <b>KsUnregisterWorker</b> function allows clients to unregister a worker. The function can destroy threads, depending on the number of threads in use. This must only be used after successful execution of <b>KsRegisterWorker</b>. The function can only be called at PASSIVE_LEVEL.


## -parameters




### -param Worker [in]

Specifies the previously allocated worker to be unregistered. The function will wait until any outstanding work item is completed.


## -returns



None




## -remarks



The client must ensure that outstanding I/O initiated on any worker thread has been completed before unregistering the worker has been completed. This means canceling or completing outstanding I/O either before unregistering the worker, or before the worker item returns from its callback for the last time and is unregistered. Unregistering of a worker will wait for any currently queued work items to complete before returning. 



