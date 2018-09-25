---
UID: NC:wdfio.EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES
title: EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES
author: windows-driver-content
description: A driver's EvtIoAllocateRequestResources callback function allocates request-specific resources that the driver requires to process the specified request.
old-location: wdf\evtioallocaterequestresources.htm
tech.root: wdf
ms.assetid: 6a60c563-582a-4919-bf0f-919deb3055d3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_85702d4a-4861-4512-a392-f106e038d3be.xml, EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES, EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES callback, EvtIoAllocateRequestResources, EvtIoAllocateRequestResources callback function, kmdf.evtioallocaterequestresources, wdf.evtioallocaterequestresources, wdfio/EvtIoAllocateRequestResources
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfio.h
api_name:
-	EvtIoAllocateRequestResources
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtIoAllocateRequestResources</i> callback function allocates request-specific resources that the driver requires to process the specified request.


## -parameters




### -param Queue [in]

A handle to an I/O queue object.


### -param Request [in]

A handle to a request object that the framework has created. The framework has not yet added the request object to the I/O queue that the <i>Queue</i> parameter's handle specifies.


## -returns



The <i>EvtIoAllocateRequestResources</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



A driver can register an <i>EvtIoAllocateRequestResources</i> callback function when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547395">WdfIoQueueAssignForwardProgressPolicy</a>.

If your driver registers an <i>EvtIoAllocateRequestResources</i> callback function, the framework calls the function immediately after it creates a request object for an I/O request packet (IRP) that the I/O manager has sent to your driver. 

The callback function can allocate resources that your driver will require to process the request later, after the driver has obtained the request object from the I/O queue that the <i>Queue</i> parameter's handle specifies.

If the callback function successfully allocates resources and returns STATUS_SUCCESS, the framework will eventually deliver the request object to the driver.

If a resource allocation error occurs, such as a low memory situation, the callback function must return an error status value. In this case, the framework follows the driver's forward progress policy, which the driver previously specified with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552357">WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY</a> value when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff547395">WdfIoQueueAssignForwardProgressPolicy</a>.

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




<a href="https://msdn.microsoft.com/07ba6437-655b-417a-87a8-5374812ca4d7">EvtIoAllocateResourcesForReservedRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547395">WdfIoQueueAssignForwardProgressPolicy</a>
 

 

