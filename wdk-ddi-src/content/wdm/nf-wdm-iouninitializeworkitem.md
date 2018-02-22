---
UID: NF:wdm.IoUninitializeWorkItem
title: IoUninitializeWorkItem function
author: windows-driver-content
description: The IoUninitializeWorkItem routine uninitializes a work item that was initialized by IoInitializeWorkItem.
old-location: kernel\iouninitializeworkitem.htm
old-project: kernel
ms.assetid: 8e7713a5-534d-42b4-a719-7b7ce911245a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.iouninitializeworkitem, wdm/IoUninitializeWorkItem, k104_05634a73-eb65-4572-a776-4dcd6b116f52.xml, IoUninitializeWorkItem routine [Kernel-Mode Driver Architecture], IoUninitializeWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoUninitializeWorkItem
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoUninitializeWorkItem function


## -description


The <b>IoUninitializeWorkItem</b> routine uninitializes a work item that was initialized by <a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>.


## -syntax


````
VOID IoUninitializeWorkItem(
  _In_ PIO_WORKITEM IoWorkItem
);
````


## -parameters




### -param IoWorkItem [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure to uninitialize. 


## -returns



None




## -remarks



Only uninitialize a work item that is not currently queued. The system dequeues a work item before it runs the work item's callback routine, so <b>IoUninitializeWorkItem</b> can be called from within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a> routine for the work item.

For more information about work items, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>. 




## -see-also

<a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoUninitializeWorkItem routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

