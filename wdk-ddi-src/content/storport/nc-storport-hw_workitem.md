---
UID: NC:storport.HW_WORKITEM
title: HW_WORKITEM
author: windows-driver-content
description: A miniport-provided callback function for processing a Storport work item request.
old-location: storage\hwstorworkitem.htm
old-project: storage
ms.assetid: CBBB1350-66BE-4F74-A0CE-0400245352F3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HW_WORKITEM, HwStorWorkItem, HwStorWorkItem routine [Storage Devices], storage.hwstorworkitem, storport/HwStorWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	storport.h
api_name:
-	HwStorWorkItem
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_WORKITEM callback


## -description


A miniport-provided callback function for processing a Storport work item request.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area. 


### -param Context [in, optional]

Optional context provided by the miniport in the <i>Callback</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451509">StorPortQueueWorkItem</a>.


### -param Worker [in]

A pointer to an opaque buffer that holds context information for the work item returned by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451486">StorPortInitializeWorker</a>.


## -returns



None.




## -remarks



If needed, a work item can be queued within <b>HwStorWorkItem</b>. Call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451509">StorPortQueueWorkItem</a> with the current work item to reuse it. Otherwise, call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451478">StorPortFreeWorker</a> to release the work item.

No locks are acquired by Storport when the callback is invoked. The miniport is responsible for any synchronization required in the callback routine.

The name <i>HwStorWorkItem</i> is just a placeholder for the miniport function that is pointed to by the <i>Callback</i> parameter of  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451509">StorPortQueueWorkItem</a>. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_WORKITEM (
    _In_     PVOID HwDeviceExtension,
    _In_Opt_ PVOID Context,
    _In_     PVOID Worker,
    );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451478">StorPortFreeWorker</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451486">StorPortInitializeWorker</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451509">StorPortQueueWorkItem</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_WORKITEM routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

