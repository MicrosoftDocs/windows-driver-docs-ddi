---
UID: NF:wdfworkitem.WdfWorkItemEnqueue
title: WdfWorkItemEnqueue function (wdfworkitem.h)
description: The WdfWorkItemEnqueue method adds a specified framework work-item object to the system's work-item queue.
old-location: wdf\wdfworkitemenqueue.htm
tech.root: wdf
ms.assetid: b264fac0-61d9-4789-b60b-c0b309eb25f1
ms.date: 02/26/2018
ms.keywords: DFWorkItemObjectRef_f2f5dbe5-20e0-4cb8-aeca-663934d0fc92.xml, WdfWorkItemEnqueue, WdfWorkItemEnqueue method, kmdf.wdfworkitemenqueue, wdf.wdfworkitemenqueue, wdfworkitem/WdfWorkItemEnqueue
ms.topic: function
f1_keywords:
 - "wdfworkitem/WdfWorkItemEnqueue"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfWorkItemEnqueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWorkItemEnqueue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfWorkItemEnqueue</b> method adds a specified framework work-item object to the system's work-item queue.


## -parameters




### -param WorkItem [in]

A handle to a framework work-item object that is obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nf-wdfworkitem-wdfworkitemcreate">WdfWorkItemCreate</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nf-wdfworkitem-wdfworkitemcreate">WdfWorkItemCreate</a> to create a work item, the driver must call <b>WdfWorkItemEnqueue</b> to add the work item to the system's work-item queue. A system worker thread subsequently removes the work item from the queue and calls the work item's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function. The system removes the work items in the order that they were added to the queue.

Before drivers call <b>WdfWorkItemEnqueue</b>, they typically use the work-item object's context memory to store information about the work item. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function uses this information to determine the operation that it must perform.

For versions 1.7 and later of KMDF, if your driver reuses its work-item objects, the driver can call <b>WdfWorkItemEnqueue</b> again for the same work item before a system worker thread has dequeued the work item and subsequently called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function. However, KMDF will not add the work item to the queue if it is already there. Therefore, your <i>EvtWorkItem</i> callback function must process all queued work each time that it is called.

Your driver can also call <b>WdfWorkItemEnqueue</b> while an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function is running, to queue another work item. The second work item's <i>EvtWorkItem</i> callback might even run before the first one completes.

In versions of KMDF prior to version 1.7, if your driver reuses its work-item objects, it must not call <b>WdfWorkItemEnqueue</b> again for the same work item until a system worker thread has dequeued the work item and called its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function. 

For more information about work items, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.


#### Examples

This section contains two examples. The first example shows how to add work items to a queue for KMDF versions 1.7 and later. The second example shows how to add work items to a queue for KMDF versions prior to version 1.7 

<b>Example 1: KMDF versions 1.7 and later</b>

The following code example calls a local routine that returns a pointer to a work-item object's context memory. The example sets information in the object's context memory and then calls <b>WdfWorkItemEnqueue</b>. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function will later retrieve the information from the work-item object.

```cpp
PMY_CONTEXT_TYPE context;

context = GetWorkItemContext(hWorkItem);
context->FdoData = FdoData;
context->Argument1 = Context1;
context->Argument2 = Context2;

WdfWorkItemEnqueue(hWorkItem);
```
The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function contains the following code. 

```cpp
MyWorkItemCallback (
    IN WDFWORKITEM hWorkItem
    )
{
    PMY_CONTEXT_TYPE context;

    context = GetWorkItemContext(hWorkItem);

    //
    // Do work here.
    //
    ...
    //
    return;
}
```
<b>Example 2: KMDF versions prior to 1.7</b>

The following code example calls a local routine that returns a pointer to a work-item object's context memory. The example sets information in the object's context memory, sets a state variable to "busy", and then calls <b>WdfWorkItemEnqueue</b>. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function will later retrieve the information from the work-item object.

```cpp
typedef enum _WORKITEM_STATE {
    WORKITEM_STATE_FREE =0,
    WORKITEM_STATE_BUSY = 1
} WORKITEM_STATE;
...
PMY_CONTEXT_TYPE context;

context = GetWorkItemContext(hWorkItem);
context->FdoData = FdoData;
context->Argument1 = Context1;
context->Argument2 = Context2;

if (InterlockedCompareExchange(
                               (PLONG)&context->WorkItemState,
                               WORKITEM_STATE_BUSY,
                               WORKITEM_STATE_FREE
                               ) == WORKITEM_STATE_FREE) {
 WdfWorkItemEnqueue(hWorkItem);
}
```
The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function contains the following code. Just before the <b>return</b> statement, the code sets the work-item object's state variable to "free" so that the driver can queue the object again.

```cpp
MyWorkItemCallback (
    IN WDFWORKITEM hWorkItem
    )
{
    PMY_CONTEXT_TYPE context;
    LONG result;

    context = GetWorkItemContext(hWorkItem);

    //
    // Do work here.
    //
    ...
    //
    // Reset object state.
    //
    result = InterlockedExchange(
                                 (PLONG)&context->WorkItemState,
                                 WORKITEM_STATE_FREE
                                 );
    ASSERT(result == WORKITEM_STATE_BUSY);
    return;
}
```
<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-interlockedcompareexchange">InterlockedCompareExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-interlockedexchange">InterlockedExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nf-wdfworkitem-wdfworkitemcreate">WdfWorkItemCreate</a>
 

 

