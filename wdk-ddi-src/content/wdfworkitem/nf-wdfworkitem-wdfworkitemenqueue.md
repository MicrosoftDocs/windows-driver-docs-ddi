---
UID: NF:wdfworkitem.WdfWorkItemEnqueue
title: WdfWorkItemEnqueue function
author: windows-driver-content
description: The WdfWorkItemEnqueue method adds a specified framework work-item object to the system's work-item queue.
old-location: wdf\wdfworkitemenqueue.htm
old-project: wdf
ms.assetid: b264fac0-61d9-4789-b60b-c0b309eb25f1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFWORKITEMENQUEUE, DFWorkItemObjectRef_f2f5dbe5-20e0-4cb8-aeca-663934d0fc92.xml, wdfworkitem/WdfWorkItemEnqueue, WdfWorkItemEnqueue, WdfWorkItemEnqueue method, kmdf.wdfworkitemenqueue, wdf.wdfworkitemenqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfworkitem.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfWorkItemEnqueue
product: Windows
targetos: Windows
req.typenames: "*PWDF_WMI_PROVIDER_CONFIG, WDF_WMI_PROVIDER_CONFIG"
req.product: Windows 10 or later.
---

# WdfWorkItemEnqueue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfWorkItemEnqueue</b> method adds a specified framework work-item object to the system's work-item queue.


## -syntax


````
VOID WdfWorkItemEnqueue(
  _In_ WDFWORKITEM WorkItem
);
````


## -parameters




### -param WorkItem [in]

A handle to a framework work-item object that is obtained from a previous call to <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


After the driver calls <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a> to create a work item, the driver must call <b>WdfWorkItemEnqueue</b> to add the work item to the system's work-item queue. A system worker thread subsequently removes the work item from the queue and calls the work item's <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function. The system removes the work items in the order that they were added to the queue.

Before drivers call <b>WdfWorkItemEnqueue</b>, they typically use the work-item object's context memory to store information about the work item. The <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function uses this information to determine the operation that it must perform.

For versions 1.7 and later of KMDF, if your driver reuses its work-item objects, the driver can call <b>WdfWorkItemEnqueue</b> again for the same work item before a system worker thread has dequeued the work item and subsequently called the driver's <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function. However, KMDF will not add the work item to the queue if it is already there. Therefore, your <i>EvtWorkItem</i> callback function must process all queued work each time that it is called.

Your driver can also call <b>WdfWorkItemEnqueue</b> while an <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function is running, to queue another work item. The second work item's <i>EvtWorkItem</i> callback might even run before the first one completes.

In versions of KMDF prior to version 1.7, if your driver reuses its work-item objects, it must not call <b>WdfWorkItemEnqueue</b> again for the same work item until a system worker thread has dequeued the work item and called its <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function. 

For more information about work items, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.



## -see-also

<a href="..\wdm\nf-wdm-interlockedexchange.md">InterlockedExchange</a>

<a href="..\wdm\nf-wdm-interlockedcompareexchange.md">InterlockedCompareExchange</a>

<a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a>

<a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWorkItemEnqueue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

