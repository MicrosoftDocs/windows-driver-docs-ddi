---
UID: NC:wdm.DMA_COMPLETION_ROUTINE
title: DMA_COMPLETION_ROUTINE
author: windows-driver-content
description: The DmaCompletionRoutine callback routine notifies the driver that previously requested a system DMA transfer that this transfer is complete.
old-location: kernel\dmacompletionroutine.htm
old-project: kernel
ms.assetid: 13EC62D0-6C70-46BE-8088-2DEC7012EE1A
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: DMA_COMPLETION_ROUTINE, DmaCompletionRoutine, DmaCompletionRoutine routine [Kernel-Mode Driver Architecture], kernel.dmacompletionroutine, wdm/DmaCompletionRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
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
req.irql: Called at DISPATCH_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	DmaCompletionRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# DMA_COMPLETION_ROUTINE callback function


## -description


The <i>DmaCompletionRoutine</i> callback routine notifies the driver that previously requested a system DMA transfer that this transfer is complete.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel.


### -param DeviceObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure. This structure is the physical device object (PDO) that represents the target device for the requested DMA operation.


### -param CompletionContext [in]

A pointer to a driver-determined context for the <i>DmaCompletionRoutine</i> routine. This context is the <i>CompletionContext</i> parameter value that the driver previously passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a> call that initiated the system DMA transfer.


### -param Status [in]

The completion status of the DMA transfer. This parameter is a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450997">DMA_COMPLETION_STATUS</a> enumeration value that indicates whether the DMA transfer completed successfully.


## -returns



None.




## -remarks



As an option, a driver can implement a <i>DmaCompletionRoutine</i> routine. When the driver requests a system DMA transfer, the driver can supply a pointer to this routine with the request. After the DMA transfer completes, the <i>DmaCompletionRoutine</i> routine is automatically called to notify the driver.

A driver's <i>DmaCompletionRoutine</i> routine is called only if the DMA transfer requested by the driver uses a system DMA controller that can generate an interrupt after a DMA transfer completes. A driver that uses a bus-master DMA device, or that uses a system DMA controller that does not generate interrupts, must use other means to determine when a DMA transfer completes. For example, this driver might use a timer interrupt to periodically poll the status of the DMA transfer.

A driver can supply a pointer to a <i>DmaCompletionRoutine</i> routine as an optional parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a> routine.


#### Examples

To define a <i>DmaCompletionRoutine</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>DmaCompletionRoutine</i> callback routine that is named <code>MyDmaCompletionRoutine</code>, use the DMA_COMPLETION_ROUTINE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DMA_COMPLETION_ROUTINE MyDmaCompletionRoutine;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
_Use_decl_annotations_
VOID
  MyDmaCompletionRoutine(
    PDMA_ADAPTER DmaAdapter,
    PDEVICE_OBJECT DeviceObject,
    PVOID CompletionContext,
    DMA_COMPLETION_STATUS Status
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The DMA_COMPLETION_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DMA_COMPLETION_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450997">DMA_COMPLETION_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451134">GetScatterGatherListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a>
 

 

