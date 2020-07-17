---
UID: NF:wdfio.WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT
title: WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function (wdfio.h)
description: The WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function initializes a driver's WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure.
old-location: wdf\wdf_io_queue_forward_progress_policy_pagingio_init.htm
tech.root: wdf
ms.assetid: e8839d4d-b7cb-4f18-b122-42c87e779d7f
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function"]
ms.keywords: DFQueueObjectRef_57ac1d7b-3417-4757-bd62-21bc8b13c782.xml, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function, kmdf.wdf_io_queue_forward_progress_policy_pagingio_init, wdf.wdf_io_queue_forward_progress_policy_pagingio_init, wdfio/WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT
f1_keywords:
 - "wdfio/WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT"
 - "WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT"
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfio.h
api_name:
- WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.


## -parameters




### -param Policy [out]

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.


### -param TotalForwardProgressRequests [in]

The number of request objects that the framework will attempt to reserve for use in low-memory situations. This number must be greater than zero.


## -remarks



The <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure and sets its <b>Size</b> member. It also sets the <b>ForwardProgressReservedPolicy</b> member to <b>WdfIoForwardProgressReservedPolicyUseExamine</b>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ns-wdfio-_wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>. In the example, the driver is specifying that the framework should allocate and reserve 10 request objects for low-memory situations, and that the framework should use one of the reserved requests during low-memory situations only if the I/O request is a paging operation.

```cpp
#define MAX_RESERVED_REQUESTS 10

WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY queueForwardProgressPolicy;
WDFQUEUE readQueue;
NTSTATUS status = STATUS_SUCCESS;

WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT(
    &queueForwardProgressPolicy,
    MAX_RESERVED_REQUESTS
    );
status = WdfIoQueueAssignForwardProgressPolicy(
    readQueue,
    &queueForwardProgressPolicy
    );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_forward_progress_policy_default_init">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_DEFAULT_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_forward_progress_policy_examine_init">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>
 

 

