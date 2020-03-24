---
UID: NC:ndis.NDIS_PD_QUERY_QUEUE_DEPTH
title: NDIS_PD_QUERY_QUEUE_DEPTH (ndis.h)
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's PDQueryQueueDepth function to return the number of unprocessed PD_BUFFER structures that are posted to the Queue.
old-location: netvista\pdqueryqueuedepth.htm
tech.root: netvista
ms.assetid: 0061E269-4A19-4D65-B988-29DB582BA960
ms.date: 05/02/2018
keywords: ["NDIS_PD_QUERY_QUEUE_DEPTH callback function"]
ms.keywords: "*NDIS_PD_QUERY_QUEUE_DEPTH_HANDLER, *NDIS_PD_QUERY_QUEUE_DEPTH_HANDLER callback function pointer [Network Drivers Starting with Windows Vista], NDIS_PD_QUERY_QUEUE_DEPTH, NDIS_PD_QUERY_QUEUE_DEPTH callback, PDQueryQueueDepth, PDQueryQueueDepth callback function [Network Drivers Starting with Windows Vista], ndis/PDQueryQueueDepth, netvista.pdqueryqueuedepth"
f1_keywords:
 - "ndis/*NDIS_PD_QUERY_QUEUE_DEPTH_HANDLER"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- *NDIS_PD_QUERY_QUEUE_DEPTH_HANDLER
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_PD_QUERY_QUEUE_DEPTH callback function


## -description


The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>PDQueryQueueDepth</i> function to return the number of unprocessed <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_pd_buffer">PD_BUFFER</a> structures that are posted to the <b>Queue</b>.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_QUERY_QUEUE_DEPTH</b> type. For more
   information, see the following Examples section.</div>
<div> </div>



## -parameters




### -param Queue [in]

A pointer to a transmit or receive queue.


### -param Depth [out]

On a receive queue, this is the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_pd_buffer">PD_BUFFER</a> structures that are available for placing incoming packets into. For example, if 10 buffers were posted, and 3 of the 10 have already been fetched by the provider for placing incoming packets into, this value should be 7. On a transmit queue, this is the number of <b>PD_BUFFER</b> structures that the provider has not yet fetched from the queue for transmitting.


## -returns



This callback function does not return a value.




## -remarks



<div class="alert"><b>Note</b>  For IHV partners: The ability to monitor the queue depth is very important for clients to access congestion build-up and take precautionary action. An increasing queue depth for a transmit queue is a sign of increasing congestion on the outbound link. A decreasing queue depth for an RX queue is a sign of the client not being able to process incoming packets fast enough on the inbound link. Clients may need to monitor the queue depth status with frequently (For example, getting the queue depth for each post and operation, therefore the cost (in CPU cycles) of querying the queue depth must not be noticeable in comparison to the cost of a single <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_pd_post_and_drain_buffer_list">PDPostAndDrainBufferList</a> call.</div>
<div> </div>
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>PDQueryQueueDepth</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>PDQueryQueueDepth</i> function that is named "MyPDQueryQueueDepth", use the <b>NDIS_PD_QUERY_QUEUE_DEPTH</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NDIS_PD_QUERY_QUEUE_DEPTH MyPDQueryQueueDepth;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyPDQueryQueueDepth(
    CONST NDIS_PD_QUEUE*  Queue,
    ULONG64*  Depth
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>NDIS_PD_QUERY_QUEUE_DEPTH</b> function type is defined in the Ntddndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_PD_QUERY_QUEUE_DEPTH</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



