---
UID: NF:storport.StorPortInitializeWorker
title: StorPortInitializeWorker function
author: windows-driver-content
description: Creates a new Storport work item that runs in a system worker thread.
old-location: storage\storportinitializeworker.htm
old-project: storage
ms.assetid: 4472A092-B2F4-4220-9685-6BE4FF0A83DB
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.storportinitializeworker, StorPortInitializeWorker routine [Storage Devices], StorPortInitializeWorker, storport/StorPortInitializeWorker
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortInitializeWorker
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortInitializeWorker function


## -description


Creates a new Storport work item that runs in a system worker thread.


## -syntax


````
ULONG StorPortInitializeWorker(
  _In_  PVOID HwDeviceExtension,
  _Out_ PVOID *Worker
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Worker [out]

A pointer to an opaque buffer that holds context information for the work item.


## -returns



The <b>StorPortInitializeWorker</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
Current IRQL &gt; DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>HwDeviceExtension</i> or <i>Worker</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
 Insufficient resources are available to initialize the work item context.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The work item was successfully initialized.

</td>
</tr>
</table>
 




## -remarks



The work item context returned in the <i>Worker</i> parameter by <b>StorPortInitializeWorker</b> is used in future calls to <a href="..\storport\nf-storport-storportqueueworkitem.md">StorPortQueueWorkItem</a> or <a href="..\storport\nf-storport-storportfreeworker.md">StorPortFreeWorker</a>.

If the miniport uses the work item during IO processing, we recommended that <b>StorPortInitializeWorker</b> be called during the miniport's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> function to ensure that resources are available when needed.




## -see-also

<a href="..\storport\nf-storport-storportqueueworkitem.md">StorPortQueueWorkItem</a>



<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>



<a href="..\storport\nf-storport-storportfreeworker.md">StorPortFreeWorker</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInitializeWorker routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

