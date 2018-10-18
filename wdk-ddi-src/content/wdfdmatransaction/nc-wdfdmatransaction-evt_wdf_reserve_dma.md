---
UID: NC:wdfdmatransaction.EVT_WDF_RESERVE_DMA
title: EVT_WDF_RESERVE_DMA
author: windows-driver-content
description: The EvtReserveDma event callback function is called when the framework has reserved resources to execute and release a transaction. Reserved resources include map registers and the WDM DMA adapter's lock.
old-location: wdf\evtreservedma.htm
tech.root: wdf
ms.assetid: 3663EF19-5F16-43D1-BFBC-28280E28D4DE
ms.date: 2/26/2018
ms.keywords: EVT_WDF_RESERVE_DMA, EVT_WDF_RESERVE_DMA callback, EvtReserveDma, EvtReserveDma callback function, kmdf.evtreservedma, wdf.evtreservedma, wdfdmatransaction/EvtReserveDma
ms.topic: callback
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	WdfDmaTransaction.h
api_name:
-	EvtReserveDma
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_RESERVE_DMA callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The 
  <i>EvtReserveDma</i> event callback function is called when the framework has reserved resources to execute and release a transaction. Reserved resources include map registers and the WDM DMA adapter's lock.


## -parameters




### -param DmaTransaction [in]

A handle to the DMA transaction object that represents the transaction to which DMA resources were assigned.


### -param Context [in]

The context pointer that the driver specified in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a>.


## -returns



This callback function does not return a value.




## -remarks



Drivers register an <i>EvtReserveDma</i> event callback function by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a>.

The framework calls a driver's <i>EvtReserveDma</i> event callback function when DMA resources have been assigned for exclusive use with the associated transaction object. The driver can initialize and execute the transaction multiple times while holding this reservation.

A driver typically initializes and then initiates the transaction from within its <i>EvtReserveDma</i> event callback function. For more information about the reservation sequence, see <a href="https://msdn.microsoft.com/8C5FF779-8D54-47D9-8EC6-7D4921F8F697">Reserving DMA Resources</a>.

  

The driver may call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451177">WdfDmaTransactionFreeResources</a> from within <i>EvtReserveDma</i>.


On operating systems earlier than Windows 8, <i>EvtReserveDma</i> must be used with an enabler that specifies a packet-mode DMA enabler.  Starting with  Windows 8, <i>EvtReserveDma</i> can also be used with an enabler that specifies a system-mode DMA enabler.


#### Examples

To define an <i>EvtReserveDma</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtReserveDma</i> callback function that is named <i>MyReserveDma</i>, use the <b>EVT_WDF_RESERVE_DMA</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_RESERVE_DMA  MyReserveDma;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
 MyReserveDma (
    WDFDMATRANSACTION DmaTransaction,
    PVOID Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_RESERVE_DMA</b> function type is defined in the WdfDmaTransaction.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_RESERVE_DMA</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451177">WdfDmaTransactionFreeResources</a>
 

 

