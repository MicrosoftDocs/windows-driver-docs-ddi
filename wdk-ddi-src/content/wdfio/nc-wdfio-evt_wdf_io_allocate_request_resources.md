---
UID: NC:wdfio.EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES
title: EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES
author: windows-driver-content
description: A driver's EvtIoAllocateRequestResources callback function allocates request-specific resources that the driver requires to process the specified request.
old-location: wdf\evtioallocaterequestresources.htm
old-project: wdf
ms.assetid: 6a60c563-582a-4919-bf0f-919deb3055d3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFQueueObjectRef_85702d4a-4861-4512-a392-f106e038d3be.xml, EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES, EvtIoAllocateRequestResources, EvtIoAllocateRequestResources callback function, kmdf.evtioallocaterequestresources, wdf.evtioallocaterequestresources, wdfio/EvtIoAllocateRequestResources
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfio.h
apiname:
-	EvtIoAllocateRequestResources
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
req.product: Windows 10 or later.
---

# EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtIoAllocateRequestResources</i> callback function allocates request-specific resources that the driver requires to process the specified request.


## -prototype


````
EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES EvtIoAllocateRequestResources;

NTSTATUS EvtIoAllocateRequestResources(
  _In_ WDFQUEUE   Queue,
  _In_ WDFREQUEST Request
)
{ ... }
````


## -parameters




### -param Queue [in]

A handle to an I/O queue object.


### -param Request [in]

A handle to a request object that the framework has created. The framework has not yet added the request object to the I/O queue that the <i>Queue</i> parameter's handle specifies.


## -returns



The <i>EvtIoAllocateRequestResources</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



A driver can register an <i>EvtIoAllocateRequestResources</i> callback function when it calls <a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>.

If your driver registers an <i>EvtIoAllocateRequestResources</i> callback function, the framework calls the function immediately after it creates a request object for an I/O request packet (IRP) that the I/O manager has sent to your driver. 

The callback function can allocate resources that your driver will require to process the request later, after the driver has obtained the request object from the I/O queue that the <i>Queue</i> parameter's handle specifies.

If the callback function successfully allocates resources and returns STATUS_SUCCESS, the framework will eventually deliver the request object to the driver.

If a resource allocation error occurs, such as a low memory situation, the callback function must return an error status value. In this case, the framework follows the driver's forward progress policy, which the driver previously specified with a <a href="..\wdfio\ne-wdfio-_wdf_io_forward_progress_reserved_policy.md">WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY</a> value when it called <a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>.

For more information about the <i>EvtIoAllocateRequestResources</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.

This callback function can be called at IRQL &lt;= DISPATCH_LEVEL. If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.


#### Examples

To define an <i>EvtIoAllocateRequestResources</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoAllocateRequestResources</i> callback function that is named <i>MyIoAllocateRequestResources</i>, use the <b>EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES  MyIoAllocateRequestResources;</pre>
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
NTSTATUS
 MyIoAllocateRequestResources (
    WDFQUEUE  Queue,
    WDFREQUEST  Request
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>



<a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request.md">EvtIoAllocateResourcesForReservedRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

