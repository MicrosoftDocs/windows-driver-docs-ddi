---
UID: NC:wdm.IO_CSQ_REMOVE_IRP
title: IO_CSQ_REMOVE_IRP
author: windows-driver-content
description: The CsqRemoveIrp routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqremoveirp.htm
old-project: kernel
ms.assetid: 9d99a20b-3a95-4e27-96bd-41f38a631573
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: CsqRemoveIrp, CsqRemoveIrp routine [Kernel-Mode Driver Architecture], DrvrRtns_6d9086c3-65b8-4e0e-b5e9-0c4edbf513b1.xml, IO_CSQ_REMOVE_IRP, kernel.csqremoveirp, wdm/CsqRemoveIrp
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	CsqRemoveIrp
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# IO_CSQ_REMOVE_IRP callback


## -description


The <i>CsqRemoveIrp</i> routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue.


## -parameters




### -param Csq [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure for the cancel-safe IRP queue.


### -param Irp [in]

Pointer to the IRP to remove from the IRP queue. 


## -returns



None




## -remarks



The driver specifies the <i>CsqRemoveIrp</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqRemoveIrp</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff549054">IoCsqInitialize</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff549070">IoCsqRemoveIrp</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549072">IoCsqRemoveNextIrp</a> routines call the cancel-safe IRP queue's <i>CsqRemoveIrp</i> routine to remove the specified IRP from the queue. The system also uses <i>CsqRemoveIrp</i> to remove a canceled IRP from the queue.


#### Examples

To define a <i>CsqRemoveIrp</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CsqRemoveIrp</i> callback routine that is named <code>MyCsqRemoveIrp</code>, use the IO_CSQ_REMOVE_IRP type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_CSQ_REMOVE_IRP MyCsqRemoveIrp;</pre>
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
 MyCsqRemoveIrp(
    PIO_CSQ  Csq,
    PIRP  Irp
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_CSQ_REMOVE_IRP function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_CSQ_REMOVE_IRP function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542934">CsqAcquireLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542940">CsqCompleteCanceledIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542947">CsqInsertIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542956">CsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542959">CsqPeekNextIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542965">CsqReleaseLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549054">IoCsqInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549066">IoCsqInsertIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549067">IoCsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549070">IoCsqRemoveIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549072">IoCsqRemoveNextIrp</a>
 

 

