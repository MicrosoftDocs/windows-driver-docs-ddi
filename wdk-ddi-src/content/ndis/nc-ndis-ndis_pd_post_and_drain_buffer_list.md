---
UID: NC:ndis.NDIS_PD_POST_AND_DRAIN_BUFFER_LIST
title: NDIS_PD_POST_AND_DRAIN_BUFFER_LIST
author: windows-driver-content
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's PDPostAndDrainBufferList function to post PD_BUFFER structures to PD transmit/receive queues and draining any previously posted PD_BUFFER structures that have been completed.
old-location: netvista\pdpostanddrainbufferlist.htm
old-project: netvista
ms.assetid: 5EAAEEEC-740E-4F65-B13E-E174A0DF4546
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*NDIS_PD_POST_AND_DRAIN_BUFFER_LIST_HANDLER, *NDIS_PD_POST_AND_DRAIN_BUFFER_LIST_HANDLER callback function [Network Drivers Starting with Windows Vista], NDIS_PD_POST_AND_DRAIN_BUFFER_LIST, NDIS_PD_POST_AND_DRAIN_BUFFER_LIST callback, PDPostAndDrainBufferList, PDPostAndDrainBufferList callback function [Network Drivers Starting with Windows Vista], ndis/PDPostAndDrainBufferList, netvista.pdpostanddrainbufferlist"
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	*NDIS_PD_POST_AND_DRAIN_BUFFER_LIST_HANDLER
product: Windows
targetos: Windows
req.typenames: 
---

# NDIS_PD_POST_AND_DRAIN_BUFFER_LIST callback function


## -description


The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>PDPostAndDrainBufferList</i> function to post <a href="https://msdn.microsoft.com/library/windows/hardware/dn931863">PD_BUFFER</a> structures to PD transmit/receive queues and draining any previously posted <b>PD_BUFFER</b> structures that have been completed.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_POST_AND_DRAIN_BUFFER_LIST</b> type. For more
   information, see the following Examples section.</div>
<div> </div>



## -parameters




### -param Queue [in, out]

A pointer to the transmit or receive queue that will receive posted buffers and will have completed buffers removed.


### -param PostBufferListHead [in, out]

The head of the post list. The provider removes the buffers in this list and adds them into the <b>Queue</b>.


### -param DrainBufferListTail [in, out]

The tail of the drain list. The provider removes any completed buffers from the <b>Queue</b> and adds them to this list.


### -param MaxDrainCount [in]

The maximum amount of <a href="https://msdn.microsoft.com/library/windows/hardware/dn931863">PD_BUFFER</a> structures to drain. The provider must ensure not exceed this amount. A set of partial <b>PD_BUFFER</b> structures that make up a single L2 packet count is 1.


## -returns



This callback function does not return a value.




## -remarks



The provider removes buffers from the PostBufferList and places them into the queue, starting with the head buffer in the list and advancing to the next buffer until either the PostBufferList is empty or the queue is full (or near full). The provider advanced to the PostListHead and returns the new list head to the caller. The provider also removes any completed buffers from the queue and inserts them into the tail of the DrainBufferList and returns the new DrainBufferList tail to the client.

<div class="alert"><b>Note</b>  The provider should drain as many buffers as it can in order to open up room for the buffers being posted. The PostBufferList and DrainBufferList are guaranteed to be disjoint buffer lists (The client never provides the head of a buffer list as the PostBufferListHead and the tail of that same list as DrainBufferListTail).</div>
<div> </div>
The client can also pass an empty post buffer list to just drain completed buffers without posting any new buffers. The client can also set the MaxDrainCount to 0 to just post new buffers without draining any completed buffers. In rare cases, the client may invoke the call with both an empty post buffer list and the MaxDrainCount to 0. The provider must not assume otherwise and handle such a call properly such as a no-operation.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>PDPostAndDrainBufferList</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>PDPostAndDrainBufferList</i> function that is named "MyPDPostAndDrainBufferList", use the <b>NDIS_PD_POST_AND_DRAIN_BUFFER_LIST</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NDIS_PD_POST_AND_DRAIN_BUFFER_LIST MyPDPostAndDrainBufferList;</pre>
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
 MyPDPostAndDrainBufferList(
    NDIS_PD_QUEUE*  Queue,
    PD_BUFFER**  PostBufferListHead,
    PD_BUFFER*** DrainBufferListTail,
    ULONG  MaxDrainCount
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>NDIS_PD_POST_AND_DRAIN_BUFFER_LIST</b> function type is defined in the Ntddndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_PD_POST_AND_DRAIN_BUFFER_LIST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 

The following is an example code snippet that illustrates the pointer indirections for this function.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>PD_BUFFER* PostHead = NULL;
PD_BUFFER** PostTail = &amp;PostHead;
PD_BUFFER* DrainHead = NULL;
PD_BUFFER** DrainTail = &amp;DrainHead;

PD_BUFFER* bufX = &lt;allocated PD_BUFFER&gt;;

bufX-&gt;NextPDBuffer = NULL;
*PostTail = bufX;
PostTail = &amp;bufX-&gt;NextPDBuffer;

// BEFORE:
//PostHead == bufX
//PostTail == &amp;bufZ-&gt;NextPDBuffer
//DrainHead == NULL
//DrainTail == &amp;DrainHead

NDIS_PD_POST_AND_DRAIN_BUFFER_LIST(
          Queue,
          &amp;PostHead,
          &amp;DrainTail,
          32);

// AFTER:
//PostHead == bufY
//PostTail == &amp;bufZ-&gt;NextPDBuffer
//DrainHead == buf1
//DrainTail == &amp;buf5-&gt;NextPDBuffer
</pre>
</td>
</tr>
</table></span></div>


