---
UID: NC:ndis.NDIS_PD_ALLOCATE_QUEUE
title: NDIS_PD_ALLOCATE_QUEUE
author: windows-driver-content
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's NdisPDAllocateQueue function to allocate a queue.
old-location: netvista\ndispdallocatequeue.htm
old-project: netvista
ms.assetid: E9091C69-0E21-40CC-B3D3-1F770ABA0D47
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndispdallocatequeue, NdisPDAllocateQueue callback function [Network Drivers Starting with Windows Vista], NdisPDAllocateQueue, NDIS_PD_ALLOCATE_QUEUE, NDIS_PD_ALLOCATE_QUEUE, ndis/NdisPDAllocateQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	NdisPDAllocateQueue
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_PD_ALLOCATE_QUEUE callback


## -description


The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>NdisPDAllocateQueue</i> function to allocate a queue.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_ALLOCATE_QUEUE</b> type. For more
   information, see the following Examples section.</div>
<div> </div>



## -prototype


````
NDIS_PD_ALLOCATE_QUEUE NdisPDAllocateQueue;

NTSTATUS NdisPDAllocateQueue(
  _In_       NDIS_PD_PROVIDER_HANDLE  ProviderHandle,
  _In_ const NDIS_PD_QUEUE_PARAMETERS *QueueParameters,
             _Outptr_ NDIS_PD_QUEUE   **NdisPDQueue
)
{ ... }
````


## -parameters




#### - ProviderHandle [in]

A provider handle that identifies the PD-capable miniport driver's provider object.


#### - QueueParameters [in]

All the parameters that are associated with the Queue. For more information see the <a href="..\ndis\ns-ndis-_ndis_pd_queue_parameters.md">NDIS_PD_QUEUE_PARAMETERS</a> structure.


#### - NdisPDQueue

A pointer to the Queue that is to be allocated. For more information, see the <a href="..\ndis\ne-ndis-ndis_pd_queue_type.md">NDIS_PD_QUEUE</a> structure.


## -returns


This function returns STATUS_SUCCESS when it completes successful, otherwise it returns the appropriate error code.



## -remarks


<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>To define a <i>NdisPDAllocateQueue</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>NdisPDAllocateQueue</i> function that is named "MyPDAllocateQueue", use the <b>NDIS_PD_ALLOCATE_QUEUE</b> type as shown in this code example:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NDIS_PD_ALLOCATE_QUEUE MyPDAllocateQueue;</pre>
</td>
</tr>
</table></span></div>Then, implement your function as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyPDAllocateQueue(
    NDIS_PD_PROVIDER_HANDLE  ProviderHandle,
    CONST NDIS_PD_QUEUE_PARAMETERS*  QueueParameters,
    NDIS_PD_QUEUE**  NdisPDQueue
    )
  {...}</pre>
</td>
</tr>
</table></span></div>The <b>NDIS_PD_ALLOCATE_QUEUE</b> function type is defined in the Ntddndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_PD_ALLOCATE_QUEUE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


