---
UID: NC:ndis.NDIS_PD_FREE_QUEUE
title: NDIS_PD_FREE_QUEUE (ndis.h)
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's NdisPDFreeQueue function to free a queue.
old-location: netvista\ndispdfreequeue.htm
tech.root: netvista
ms.assetid: 1DE8582C-AF11-4CBA-8F4C-159266A7F3BA
ms.date: 05/02/2018
ms.keywords: NDIS_PD_FREE_QUEUE, NDIS_PD_FREE_QUEUE callback, NdisPDFreeQueue, NdisPDFreeQueue callback function [Network Drivers Starting with Windows Vista], ndis/NdisPDFreeQueue, netvista.ndispdfreequeue
ms.topic: callback
f1_keywords:
 - "ndis/NdisPDFreeQueue"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- NdisPDFreeQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_PD_FREE_QUEUE callback function


## -description


The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>NdisPDFreeQueue</i> function to free a queue.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_FREE_QUEUE</b> type. For more
   information, see the following Examples section.</div>
<div> </div>



## -parameters




### -param NdisPDQueue [in]

Any empty queue that needs to be freed from memory. For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_pd_queue">NDIS_PD_QUEUE</a> structure.


## -returns



This callback function does not return a value.




## -remarks



The caller is responsible for ensuring that the PD queue is empty before issuing this call. Caller is also responsible for clearing all filters that target this queue before closing the queue.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>NdisPDFreeQueue</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>NdisPDFreeQueue</i> function that is named "MyPDFreeQueue", use the <b>NDIS_PD_FREE_QUEUE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NDIS_PD_FREE_QUEUE MyPDFreeQueue;</pre>
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
 MyPDFreeQueue(
    NDIS_PD_QUEUE*  NdisPDQueue
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>NDIS_PD_FREE_QUEUE</b> function type is defined in the Ntddndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_PD_FREE_QUEUE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



