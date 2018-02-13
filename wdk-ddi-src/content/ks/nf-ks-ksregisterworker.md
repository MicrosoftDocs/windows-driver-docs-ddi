---
UID: NF:ks.KsRegisterWorker
title: KsRegisterWorker function
author: windows-driver-content
description: The KsRegisterWorker function handles clients registering for use of a thread.
old-location: stream\ksregisterworker.htm
old-project: stream
ms.assetid: b9c74a56-3f2c-4b94-8fb2-6b44075ec34b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsRegisterWorker, ksfunc_c2cb48b6-6268-4d53-a81b-07c1984f80aa.xml, stream.ksregisterworker, KsRegisterWorker, KsRegisterWorker function [Streaming Media Devices]
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
-	KsRegisterWorker
product: Windows
targetos: Windows
req.typenames: 
---

# KsRegisterWorker function


## -description


The <b>KsRegisterWorker</b> function handles clients registering for use of a thread. The function can create a new thread of the specified priority if there are currently no free threads available. This must be matched by a corresponding <b>KsUnregisterWorker</b> when thread use is completed. The function can only be called at PASSIVE_LEVEL.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef PVOID PKSWORKER; </pre>
</td>
</tr>
</table></span></div>The worker routines function on opaque PKSWORKER objects that are created for each work item queued at one time.


## -syntax


````
typedef PVOID PKSWORKER; 
````


## -parameters




### -param WorkQueueType [in]

Specifies the priority of the thread to create. This is usually either CriticalWorkQueue<b>, </b>DelayedWorkQueue, or HyperCriticalWorkQueue<b>.</b>


### -param Worker [out]

Location to put the opaque context that must be used when scheduling a work item. This contains the queue type and is used to synchronize completion of work items.


## -returns



The <b>KsRegisterWorker</b> function returns STATUS_SUCCESS if a worker was initialized, or if unsuccessful the function returns a thread or parameter error.



