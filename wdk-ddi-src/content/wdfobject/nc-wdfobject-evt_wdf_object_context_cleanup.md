---
UID: NC:wdfobject.EVT_WDF_OBJECT_CONTEXT_CLEANUP
title: EVT_WDF_OBJECT_CONTEXT_CLEANUP (wdfobject.h)
description: A driver's EvtCleanupCallback event callback function removes the driver's references on an object so that the object can be deleted.
old-location: wdf\evtcleanupcallback.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_OBJECT_CONTEXT_CLEANUP callback function"]
ms.keywords: DFGenObjectRef_aef7bd25-42a4-41d2-9ba1-1b1113159657.xml, EVT_WDF_OBJECT_CONTEXT_CLEANUP, EVT_WDF_OBJECT_CONTEXT_CLEANUP callback, EvtCleanupCallback, EvtCleanupCallback callback function, kmdf.evtcleanupcallback, wdf.evtcleanupcallback, wdfobject/EvtCleanupCallback
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_OBJECT_CONTEXT_CLEANUP
 - wdfobject/EVT_WDF_OBJECT_CONTEXT_CLEANUP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfobject.h
api_name:
 - EvtCleanupCallback
---

# EVT_WDF_OBJECT_CONTEXT_CLEANUP callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtCleanupCallback</i> event callback function removes the driver's references on an object so that the object can be deleted.

## -parameters

### -param Object 

[in]
A handle to a framework object.

## -remarks

The driver can specify an <i>EvtCleanupCallback</i> callback function in a <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. This structure is used as input to all of the framework methods that create framework objects, such as <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. 

The framework calls the callback function when either the framework or a driver attempts to delete the object. 

If the driver has called <a href="/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a> to increase the reference count of an object, the driver must provide an <i>EvtCleanupCallback</i> callback function that calls <a href="/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a>. This call ensures that the object's reference count is decremented to zero and, as a result, the framework can call the driver's <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function and then delete the object.

If a driver supplies both an <i>EvtCleanupCallback</i> callback function and an <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function for a object, the framework calls the <i>EvtCleanupCallback</i> callback function first.

After the framework calls an object's <i>EvtCleanupCallback</i> callback function, the driver can access the object only from its <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function. However, a driver should not  attempt to call methods on an object from its EvtDestroyCallback.

When a driver creates an object, it sometimes allocates object-specific memory buffers and stores the buffer pointers in the object's <a href="/windows-hardware/drivers/wdf/framework-object-context-space">context space</a>. The driver's <i>EvtCleanupCallback</i> or <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function can deallocate these memory buffers. 

Typically, if your driver does not call <a href="/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a> for an object, the object's <i>EvtCleanupCallback</i> callback function can deallocate object context allocations. In this case, the driver does not need an <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function for the object.

When an object is deleted, the framework also deletes the object's children. With one exception, the framework calls the <i>EvtCleanupCallback</i> routines of child objects before calling those of their parent objects, so drivers are guaranteed that the parent object still exists when a child's <i>EvtCleanupCallback</i> routine runs.

The exception to this guaranteed ordering applies to I/O requests that the driver completes at DISPATCH_LEVEL. If such an I/O request object has one or more children whose <i>EvtCleanupCallback</i> routines must be called at PASSIVE_LEVEL, the parent request might be deleted before one or more of its children. An object requires cleanup at PASSIVE_LEVEL if it must wait for something to complete or if it accesses paged memory.

If the driver attempts to delete such an object (or the parent of such an object) while it is running at DISPATCH_LEVEL, the framework queues the <i>EvtCleanupCallback</i> to a work item for later processing at PASSIVE_LEVEL and then calls the cleanup callback for the parent object without determining whether the callbacks for the children have run.

To avoid any problems that might result from this behavior, drivers should not set the request object as the parent for any object that requires cleanup at PASSIVE_LEVEL. By default, the parent for most objects is WDFDEVICE, so drivers should just accept the default. Generally, if the WDFDEVICE object is passed as a parameter (either directly or as part of a structure) to the method that creates the object, the WDFDEVICE is the default parent. For a complete list of default parents, see <a href="/windows-hardware/drivers/wdf/summary-of-framework-objects">Summary of Framework Objects</a>.



 If the above exception does not apply, the framework calls the child object's <i>EvtCleanupCallback</i> callback functions before calling the parent object's <i>EvtCleanupCallback</i> callback function. Next, if the child's reference count is zero, the framework calls the child object's <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function. Finally, if the parent's reference count is zero, the framework calls the parent object's <i>EvtDestroyCallback</i> callback function.

For more information about deleting framework objects, see <a href="/windows-hardware/drivers/wdf/framework-object-life-cycle">Framework Object Life Cycle</a>.

Typically, the framework calls the <i>EvtCleanupCallback</i> callback function at IRQL <= DISPATCH_LEVEL. However, the framework calls the callback function at IRQL = PASSIVE_LEVEL in the following situations:

<ul>
<li>
The object's handle type is WDFDEVICE, WDFDRIVER, WDFDPC, WDFINTERRUPT, WDFIOTARGET, WDFQUEUE, WDFSTRING, WDFTIMER, or WDFWORKITEM.

</li>
<li>
The object's handle type is WDFMEMORY or WDFLOOKASIDE, and the driver has specified <b>PagedPool</b> for the <i>PoolType</i> parameter to <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a> or <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdflookasidelistcreate">WdfLookasideListCreate</a>.

</li>
</ul>
When a work-item object is deleted, either explicitly or because the work item's parent object is being deleted, then before calling the work item's <i>EvtCleanupCallback</i> callback function, the framework waits until all instances of the work item's <a href="/windows-hardware/drivers/ddi/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function have returned. For more information, see <a href="/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdfworkitemenqueue">WdfWorkItemEnqueue</a>.

Similarly, when a timer object is deleted, either explicitly or because the timer's parent object is being deleted, then before calling the timer's <i>EvtCleanupCallback</i> callback function, the framework waits until all instances of the timer's <a href="/windows-hardware/drivers/ddi/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a> event callback function have returned.

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

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a>



<a href="/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a>



<a href="/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdfworkitemflush">WdfWorkItemFlush</a>
