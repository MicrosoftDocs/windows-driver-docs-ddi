---
UID: NC:wdfobject.EVT_WDF_OBJECT_CONTEXT_CLEANUP
title: EVT_WDF_OBJECT_CONTEXT_CLEANUP (wdfobject.h)
description: A driver's EvtCleanupCallback event callback function removes the driver's references on an object so that the object can be deleted.
old-location: wdf\evtcleanupcallback.htm
tech.root: wdf
ms.assetid: aba2efca-7d1f-4594-af65-13356f0e3f8b
ms.date: 02/26/2018
ms.keywords: DFGenObjectRef_aef7bd25-42a4-41d2-9ba1-1b1113159657.xml, EVT_WDF_OBJECT_CONTEXT_CLEANUP, EVT_WDF_OBJECT_CONTEXT_CLEANUP callback, EvtCleanupCallback, EvtCleanupCallback callback function, kmdf.evtcleanupcallback, wdf.evtcleanupcallback, wdfobject/EvtCleanupCallback
ms.topic: callback
f1_keywords:
 - "wdfobject/EvtCleanupCallback"
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfobject.h
api_name:
- EvtCleanupCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_OBJECT_CONTEXT_CLEANUP callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtCleanupCallback</i> event callback function removes the driver's references on an object so that the object can be deleted.


## -parameters




### -param Object [in]

A handle to a framework object.


## -returns



None




## -remarks



The driver can specify an <i>EvtCleanupCallback</i> callback function in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. This structure is used as input to all of the framework methods that create framework objects, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. 

The framework calls the callback function when either the framework or a driver attempts to delete the object. 

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a> to increase the reference count of an object, the driver must provide an <i>EvtCleanupCallback</i> callback function that calls <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a>. This call ensures that the object's reference count is decremented to zero and, as a result, the framework can call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function and then delete the object.

If a driver supplies both an <i>EvtCleanupCallback</i> callback function and an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function for a object, the framework calls the <i>EvtCleanupCallback</i> callback function first.

After the framework calls an object's <i>EvtCleanupCallback</i> callback function, the driver can access the object only from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function. However, a driver should not  attempt to call methods on an object from its EvtDestroyCallback.

When a driver creates an object, it sometimes allocates object-specific memory buffers and stores the buffer pointers in the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space">context space</a>. The driver's <i>EvtCleanupCallback</i> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function can deallocate these memory buffers. 

Typically, if your driver does not call <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a> for an object, the object's <i>EvtCleanupCallback</i> callback function can deallocate object context allocations. In this case, the driver does not need an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function for the object.

When an object is deleted, the framework also deletes the object's children. With one exception, the framework calls the <i>EvtCleanupCallback</i> routines of child objects before calling those of their parent objects, so drivers are guaranteed that the parent object still exists when a child's <i>EvtCleanupCallback</i> routine runs.

The exception to this guaranteed ordering applies to I/O requests that the driver completes at DISPATCH_LEVEL. If such an I/O request object has one or more children whose <i>EvtCleanupCallback</i> routines must be called at PASSIVE_LEVEL, the parent request might be deleted before one or more of its children. An object requires cleanup at PASSIVE_LEVEL if it must wait for something to complete or if it accesses paged memory.

If the driver attempts to delete such an object (or the parent of such an object) while it is running at DISPATCH_LEVEL, the framework queues the <i>EvtCleanupCallback</i> to a work item for later processing at PASSIVE_LEVEL and then calls the cleanup callback for the parent object without determining whether the callbacks for the children have run.

To avoid any problems that might result from this behavior, drivers should not set the request object as the parent for any object that requires cleanup at PASSIVE_LEVEL. By default, the parent for most objects is WDFDEVICE, so drivers should just accept the default. Generally, if the WDFDEVICE object is passed as a parameter (either directly or as part of a structure) to the method that creates the object, the WDFDEVICE is the default parent. For a complete list of default parents, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/summary-of-framework-objects">Summary of Framework Objects</a>.



 If the above exception does not apply, the framework calls the child object's <i>EvtCleanupCallback</i> callback functions before calling the parent object's <i>EvtCleanupCallback</i> callback function. Next, if the child's reference count is zero, the framework calls the child object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function. Finally, if the parent's reference count is zero, the framework calls the parent object's <i>EvtDestroyCallback</i> callback function.

For more information about deleting framework objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-life-cycle">Framework Object Life Cycle</a>.

Typically, the framework calls the <i>EvtCleanupCallback</i> callback function at IRQL <= DISPATCH_LEVEL. However, the framework calls the callback function at IRQL = PASSIVE_LEVEL in the following situations:

<ul>
<li>
The object's handle type is WDFDEVICE, WDFDRIVER, WDFDPC, WDFINTERRUPT, WDFIOTARGET, WDFQUEUE, WDFSTRING, WDFTIMER, or WDFWORKITEM.

</li>
<li>
The object's handle type is WDFMEMORY or WDFLOOKASIDE, and the driver has specified <b>PagedPool</b> for the <i>PoolType</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdflookasidelistcreate">WdfLookasideListCreate</a>.

</li>
</ul>
When a work-item object is deleted, either explicitly or because the work item's parent object is being deleted, then before calling the work item's <i>EvtCleanupCallback</i> callback function, the framework waits until all instances of the work item's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function have returned. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nf-wdfworkitem-wdfworkitemenqueue">WdfWorkItemEnqueue</a>.

Similarly, when a timer object is deleted, either explicitly or because the timer's parent object is being deleted, then before calling the timer's <i>EvtCleanupCallback</i> callback function, the framework waits until all instances of the timer's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a> event callback function have returned.

Beginning with version 1.9 of the framework, the <i>wdfroletypes.h</i> header file contains some alternative, object type-specific, function types for the <i>EvtCleanupCallback</i> callback function. These alternative types help verification tools to determine whether the driver is properly using the callback function. Use the following table to determine which function type to use.

<table>
<tr>
<th>Object Type</th>
<th>Function Type</th>
</tr>
<tr>
<td>
Device object

</td>
<td>
EVT_WDF_DEVICE_CONTEXT_CLEANUP

</td>
</tr>
<tr>
<td>
I/O queue object

</td>
<td>
EVT_WDF_IO_QUEUE_CONTEXT_CLEANUP_CALLBACK

</td>
</tr>
<tr>
<td>
File object

</td>
<td>
EVT_WDF_FILE_CONTEXT_CLEANUP_CALLBACK

</td>
</tr>
<tr>
<td>
All other objects

</td>
<td>
EVT_WDF_OBJECT_CONTEXT_CLEANUP

</td>
</tr>
</table>
 


#### Examples

To define an <i>EvtCleanupCallback</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtCleanupCallback</i> callback function that is named <i>MyCleanupCallback</i>, use the <b>EVT_WDF_OBJECT_CONTEXT_CLEANUP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_OBJECT_CONTEXT_CLEANUP MyCleanupCallback;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID 
 MyCleanupCallback (
    WDFOBJECTObject
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_OBJECT_CONTEXT_CLEANUP</b> function type is defined in the Wdfobject.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_OBJECT_CONTEXT_CLEANUP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfworkitem/nf-wdfworkitem-wdfworkitemflush">WdfWorkItemFlush</a>
 

 

