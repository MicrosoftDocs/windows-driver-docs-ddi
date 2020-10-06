---
UID: NC:wdfobject.EVT_WDF_OBJECT_CONTEXT_DESTROY
title: EVT_WDF_OBJECT_CONTEXT_DESTROY (wdfobject.h)
description: A driver's EvtDestroyCallback event callback function performs operations that are associated with the deletion of a framework object.
old-location: wdf\evtdestroycallback.htm
tech.root: wdf
ms.assetid: 4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3
ms.date: 02/26/2018
keywords: ["EVT_WDF_OBJECT_CONTEXT_DESTROY callback function"]
ms.keywords: DFGenObjectRef_a9194b33-b67b-43bb-8d50-d918576769c0.xml, EVT_WDF_OBJECT_CONTEXT_DESTROY, EVT_WDF_OBJECT_CONTEXT_DESTROY callback, EvtDestroyCallback, EvtDestroyCallback callback function, kmdf.evtdestroycallback, wdf.evtdestroycallback, wdfobject/EvtDestroyCallback
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
 - EVT_WDF_OBJECT_CONTEXT_DESTROY
 - wdfobject/EVT_WDF_OBJECT_CONTEXT_DESTROY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfobject.h
api_name:
 - EvtDestroyCallback
---

# EVT_WDF_OBJECT_CONTEXT_DESTROY callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDestroyCallback</i> event callback function performs operations that are associated with the deletion of a framework object.

## -parameters

### -param Object 

[in]
A handle to a framework object.

## -remarks

The driver can specify an <i>EvtDestroyCallback</i> callback function in a <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. This structure is used as input to all of the framework methods that create framework objects, such as <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. 

The framework calls the <i>EvtDestroyCallback</i> callback function after the object's reference count has been decremented to zero. The framework deletes the object immediately after the <i>EvtDestroyCallback</i> callback function returns.

The <i>EvtDestroyCallback</i> can access the object context but cannot call any methods on the object.

If a driver supplies both an <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> callback function and an <i>EvtDestroyCallback</i> callback function for a object, the framework calls the <i>EvtCleanupCallback</i> callback function first.

When an object is deleted, the framework also deletes the object's children. The framework calls the child objects' <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> callback functions before calling the parent object's <i>EvtCleanupCallback</i> callback function. Next, if the child's reference count is zero, the framework calls the child object's <i>EvtDestroyCallback</i> callback function. Finally, if the parent's reference count is zero, the framework calls the parent object's <i>EvtDestroyCallback</i> callback function.

When a driver creates an object, it sometimes allocates object-specific memory buffers and stores the buffer pointers in the object's <a href="/windows-hardware/drivers/wdf/framework-object-context-space">context space</a>. The driver's <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <i>EvtDestroyCallback</i> callback function can deallocate these memory buffers. 

For more information about deleting framework objects, see <a href="/windows-hardware/drivers/wdf/framework-object-life-cycle">Framework Object Life Cycle</a>.

Typically, the framework calls the <i>EvtDestroyCallback</i> callback function at IRQL <= DISPATCH_LEVEL. However, the framework calls the callback function at IRQL = PASSIVE_LEVEL in the following situations:

<ul>
<li>
The object's handle type is WDFDEVICE, WDFDRIVER, WDFDPC, WDFINTERRUPT, WDFIOTARGET, WDFQUEUE, WDFSTRING, WDFTIMER, or WDFWORKITEM.

</li>
<li>
The object's handle type is WDFMEMORY or WDFLOOKASIDE, and the driver has specified <b>PagedPool</b> for the <i>PoolType</i> parameter to <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a> or <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdflookasidelistcreate">WdfLookasideListCreate</a>.

</li>
</ul>
Beginning with version 1.9 of the framework, the <i>wdfroletypes.h</i> header file contains some alternative, object type-specific, function types for the <i>EvtDestroyCallback</i> callback function. These alternative types help verification tools to determine whether the driver is properly using the callback function. Use the following table to determine which function type to use.

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
EVT_WDF_DEVICE_CONTEXT_DESTROY

</td>
</tr>
<tr>
<td>
I/O queue object

</td>
<td>
EVT_WDF_IO_QUEUE_CONTEXT_DESTROY_CALLBACK

</td>
</tr>
<tr>
<td>
File object

</td>
<td>
EVT_WDF_FILE_CONTEXT_DESTROY_CALLBACK

</td>
</tr>
<tr>
<td>
All other objects

</td>
<td>
EVT_WDF_OBJECT_CONTEXT_DESTROY

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>