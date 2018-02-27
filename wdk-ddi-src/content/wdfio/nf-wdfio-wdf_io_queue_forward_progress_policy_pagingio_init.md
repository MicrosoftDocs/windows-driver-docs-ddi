---
UID: NF:wdfio.WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT
title: WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function
author: windows-driver-content
description: The WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function initializes a driver's WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure.
old-location: wdf\wdf_io_queue_forward_progress_policy_pagingio_init.htm
old-project: wdf
ms.assetid: e8839d4d-b7cb-4f18-b122-42c87e779d7f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFQueueObjectRef_57ac1d7b-3417-4757-bd62-21bc8b13c782.xml, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function, kmdf.wdf_io_queue_forward_progress_policy_pagingio_init, wdf.wdf_io_queue_forward_progress_policy_pagingio_init, wdfio/WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfio.h
apiname:
-	WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT</b> function initializes a driver's <a href="..\wdfio\ns-wdfio-_wdf_io_queue_forward_progress_policy.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.


## -syntax


````
VOID WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT(
  _Out_ PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY Policy,
  _In_  ULONG                                 TotalForwardProgressRequests
);
````


## -parameters




### -param Policy [out]

A pointer to the driver's <a href="..\wdfio\ns-wdfio-_wdf_io_queue_forward_progress_policy.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.


### -param TotalForwardProgressRequests [in]

The number of request objects that the framework will attempt to reserve for use in low-memory situations. This number must be greater than zero.


## -returns



None.




## -remarks



The <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT</b> function zeros the specified <a href="..\wdfio\ns-wdfio-_wdf_io_queue_forward_progress_policy.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure and sets its <b>Size</b> member. It also sets the <b>ForwardProgressReservedPolicy</b> member to <b>WdfIoForwardProgressReservedPolicyUseExamine</b>.


#### Examples

The following code example initializes a <a href="..\wdfio\ns-wdfio-_wdf_io_queue_forward_progress_policy.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure and then calls <a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>. In the example, the driver is specifying that the framework should allocate and reserve 10 request objects for low-memory situations, and that the framework should use one of the reserved requests during low-memory situations only if the I/O request is a paging operation.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define MAX_RESERVED_REQUESTS 10

WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY queueForwardProgressPolicy;
WDFQUEUE readQueue;
NTSTATUS status = STATUS_SUCCESS;

WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT(
    &amp;queueForwardProgressPolicy,
    MAX_RESERVED_REQUESTS
    );
status = WdfIoQueueAssignForwardProgressPolicy(
    readQueue,
    &amp;queueForwardProgressPolicy
    );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_forward_progress_policy_default_init.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_DEFAULT_INIT</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_forward_progress_policy_examine_init.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

