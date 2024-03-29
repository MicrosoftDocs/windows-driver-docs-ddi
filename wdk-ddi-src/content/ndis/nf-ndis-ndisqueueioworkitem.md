---
UID: NF:ndis.NdisQueueIoWorkItem
title: NdisQueueIoWorkItem function (ndis.h)
description: NDIS drivers call the NdisQueueIoWorkItem function to queue a work item.
old-location: netvista\ndisqueueioworkitem.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisQueueIoWorkItem function"]
ms.keywords: NdisQueueIoWorkItem, NdisQueueIoWorkItem function [Network Drivers Starting with Windows Vista], ndis/NdisQueueIoWorkItem, ndis_work_items_ref_ac034ba5-7f33-4769-9664-2b9bbb5ad9e6.xml, netvista.ndisqueueioworkitem
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisQueueIoWorkItem
 - ndis/NdisQueueIoWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisQueueIoWorkItem
---

# NdisQueueIoWorkItem function


## -description

NDIS drivers call the 
  <b>NdisQueueIoWorkItem</b> function to queue a work item.

## -parameters

### -param NdisIoWorkItemHandle [in]


A handle to a private <a href="/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure that was returned by a previous call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateioworkitem">
     NdisAllocateIoWorkItem</a> function.

### -param Routine [in]


The entry point to the function that NDIS calls to process the work item. NDIS calls this routine
     in the context of a system thread. 

<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_IO_WORKITEM_FUNCTION</b> type (not <b>NDIS_IO_WORKITEM_ROUTINE</b>). For more
   information, see the following Examples section.</div>
<div> </div>
The routine includes the following input parameters:





#### WorkItemContext

A pointer to the context area that the driver passed to the 
       <i>WorkItemContext</i> parameter of 
       <b>NdisQueueIoWorkItem</b>.



#### NdisIoWorkItemHandle

A handle to a private <b>NDIS_IO_WORKITEM</b> structure that was returned by a previous call to the 
       <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateioworkitem">
     NdisAllocateIoWorkItem</a> function.

### -param WorkItemContext [in]


A pointer to a caller-supplied context area that NDIS passes through to the callback routine. 
     <i>WorkItemContext</i> can be any caller-specified data that the driver requires to manage the work
     item.

## -remarks

<b>NdisQueueIoWorkItem</b> calls 
    <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a> to queue a work item. NDIS
    work items use the 
    <b>CriticalWorkQueue</b> queue type.

The caller-supplied callback routine (NDIS_IO_WORKITEM_ROUTINE) runs in a system thread context at
    IRQL = PASSIVE_LEVEL.

This caller-supplied routine can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreeioworkitem">NdisFreeIoWorkItem</a> function to reclaim
    the storage allocated for the work item.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>Routine</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>Routine</i> function that is named "MyWorkitemRoutine", use the <b>NDIS_IO_WORKITEM_FUNCTION</b> type as shown in this code example:


```
NDIS_IO_WORKITEM_FUNCTION MyWorkitemRoutine;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyWorkitemRoutine(
    PVOID   WorkItemContext,
    NDIS_HANDLE  NdisIoWorkItemHandle
    )
  {...}
```

The <b>NDIS_IO_WORKITEM_FUNCTION</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_IO_WORKITEM_FUNCTION</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="/windows-hardware/drivers/network/ndis-i-o-work-items">NDIS I/O Work Items</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateioworkitem">NdisAllocateIoWorkItem</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreeioworkitem">NdisFreeIoWorkItem</a>
