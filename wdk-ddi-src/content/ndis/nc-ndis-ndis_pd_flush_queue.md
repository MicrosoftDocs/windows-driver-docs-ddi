---
UID: NC:ndis.NDIS_PD_FLUSH_QUEUE
title: NDIS_PD_FLUSH_QUEUE (ndis.h)
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's PDFlushQueue function to flush a specified queue, ensuring that any items that are not yet in a complete state in the queue will be completed imminently.
old-location: netvista\pdflushqueue.htm
tech.root: netvista
ms.assetid: 885EC5F7-1C7E-473F-BA2A-B4DDD54A59D2
ms.date: 05/02/2018
ms.keywords: NDIS_PD_FLUSH_QUEUE_HANDLER, NDIS_PD_FLUSH_QUEUE_HANDLER callback function
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NDIS_PD_FLUSH_QUEUE
 - ndis/NDIS_PD_FLUSH_QUEUE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - NDIS_PD_FLUSH_QUEUE_HANDLER
product:
 - Windows
---

# NDIS_PD_FLUSH_QUEUE callback function


## -description

The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>PDFlushQueue</i> function to flush a specified queue, ensuring that any items that are not yet in a complete state in the queue will be completed imminently.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_FLUSH_QUEUE</b> type. For more
   information, see the following Examples section.</div>
<div> </div>

## -parameters

### -param Queue 

[in, out]
The queue to flush. For more information, see the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_pd_queue">NDIS_PD_QUEUE</a> structure.

## -returns

This callback function does not return a value.

## -remarks

The caller is responsible for waiting for and draining all previously posted requests before closing the queue. The caller must not post any further <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_pd_buffer">PD_BUFFER</a> structures to the queue after this call. The primary use case for this routine is flushing the receive queues--if there's no incoming traffic, posted buffers will sit in the receive queue indefinitely, and these need to be drained by being flushed before the queue can be closed. The same issue does not exist for transmit queues in practice because transmit requests will not pend indefinitely. However, providers must honor the flush call for transmit queues (this may be a no-operation if the provider knows that the pending transmit request will complete very soon, which is the typical case except for L2 flow control).

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>PDFlushQueue</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>PDFlushQueue</i> function that is named "MyPDFlushQueue", use the <b>NDIS_PD_FLUSH_QUEUE</b> type as shown in this code example:


```
NDIS_PD_FLUSH_QUEUE MyPDFlushQueue;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyPDFlushQueue(
    NDIS_PD_QUEUE*  NdisPDQueue
    )
  {...}
```

The <b>NDIS_PD_FLUSH_QUEUE</b> function type is defined in the Ntddndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_PD_FLUSH_QUEUE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.