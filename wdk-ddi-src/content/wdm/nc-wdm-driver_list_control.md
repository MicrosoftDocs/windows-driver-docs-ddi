---
UID: NC:wdm.DRIVER_LIST_CONTROL
title: DRIVER_LIST_CONTROL
author: windows-driver-content
description: The AdapterListControl routine starts a direct memory access (DMA) scatter/gather operation.
old-location: kernel\adapterlistcontrol.htm
old-project: kernel
ms.assetid: 9fb49710-5d8c-4376-9898-7f0ae570ee94
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: AdapterListControl, AdapterListControl routine [Kernel-Mode Driver Architecture], DRIVER_LIST_CONTROL, DrvrRtns_feb5903f-df38-4471-ab1e-2e6341620774.xml, kernel.adapterlistcontrol, wdm/AdapterListControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
-	AdapterListControl
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# DRIVER_LIST_CONTROL callback


## -description


The <i>AdapterListControl</i> routine starts a direct memory access (DMA) scatter/gather operation.


## -parameters




### -param DeviceObject [in]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.


### -param Irp [in]

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure that describes the I/O operation, if the driver has a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine. Otherwise, not used.


### -param ScatterGather [in]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a> structure describing scatter/gather regions.


### -param Context [in]

Caller-supplied pointer to driver-defined context information, specified in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>. 


## -returns



None




## -remarks



To register an <i>AdapterListControl</i> routine for a specific device object, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> to obtain an adapter object, then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a> to request use of the adapter and to supply the <i>AdapterListControl</i> routine's address. When the adapter is free, the system calls the <i>AdapterListControl</i> routine.


#### Examples

To define an <i>AdapterListControl</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>AdapterListControl</i> callback routine that is named <code>MyAdapterListControl</code>, use the DRIVER_LIST_CONTROL type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DRIVER_LIST_CONTROL MyAdapterListControl;</pre>
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
<pre>_Use_decl_annotations_
VOID
  MyAdapterListControl(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp,
    PSCATTER_GATHER_LIST  ScatterGather,
    PVOID  Context
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The DRIVER_LIST_CONTROL function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_LIST_CONTROL function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

For detailed information about implementing an <i>AdapterListControl</i> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565510">Using Scatter/Gather DMA</a>. 

<div class="code"></div>


