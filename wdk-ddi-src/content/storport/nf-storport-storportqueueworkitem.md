---
UID: NF:storport.StorPortQueueWorkItem
title: StorPortQueueWorkItem function
author: windows-driver-content
description: Schedules a Storport work item to execute within the context of a system worker thread.
old-location: storage\storportqueueworkitem.htm
old-project: storage
ms.assetid: 7B5DD97C-2E3D-4FF7-BF04-36F016B0C6B3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortQueueWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortQueueWorkItem
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortQueueWorkItem function



## -description
Schedules a Storport work item to execute within the context of  a system worker thread.



## -syntax

````
ULONG StorPortQueueWorkItem(
  _In_     PVOID        HwDeviceExtension,
  _In_     PHW_WORKITEM WorkItemCallback,
  _In_     PVOID        Worker,
  _In_opt_ PVOID        Context
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param WorkItemCallback [in]

A pointer to a work item callback routine supplied by the miniport. This routine is called in context of the system thread to process the scheduled <i>WorkItem</i>.


### -param Worker [in]

A pointer to an opaque buffer for the worker returned by <a href="..\storport\nf-storport-storportinitializeworker.md">StorPortInitializeWorker</a>.


### -param Context [in, optional]

Optional context for the <i>WorkItem</i> that is processed by the callback routine in <i>WorkItemCallback</i>.


## -returns
The <b>StorPortQueueWorkItem</b> routine returns one of these status codes:
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>Current IRQL &gt; DISPATCH_LEVEL.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl><i>HwDeviceExtension</i>, <i>Worker</i>, or <i>WorkItemCallback</i> is NULL.
<dl>
<dt><b>STOR_STATUS_BUSY</b></dt>
</dl>The work item was is already queued for processing.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The work item was successfully queued.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\storport\nc-storport-hw_workitem.md">HwStorWorkItem</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportfreeworker.md">StorPortFreeWorker</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportinitializeworker.md">StorPortInitializeWorker</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortQueueWorkItem routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

