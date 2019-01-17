---
UID: NF:wdfinterrupt.WdfInterruptSynchronize
title: WdfInterruptSynchronize function
description: The WdfInterruptSynchronize method executes a specified callback function at the device's DIRQL while holding an interrupt object's spin lock.
old-location: wdf\wdfinterruptsynchronize.htm
tech.root: wdf
ms.assetid: b41fc37a-d41f-49ca-848f-844e049dd987
ms.date: 02/26/2018
ms.keywords: DFInterruptObjectRef_d56eadd2-4636-43bb-b842-318243bcf192.xml, WdfInterruptSynchronize, WdfInterruptSynchronize method, kmdf.wdfinterruptsynchronize, wdf.wdfinterruptsynchronize, wdfinterrupt/WdfInterruptSynchronize
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfInterruptSynchronize
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptSynchronize function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptSynchronize</b> method executes a specified callback function at the device's DIRQL while holding an interrupt object's spin lock.

For passive level interrupt objects, this method executes a specified callback function at passive level while holding an interrupt object's passive-level interrupt lock.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param Callback [in]

A pointer to an <a href="https://msdn.microsoft.com/ac73b23d-7742-43a4-8950-b301bd0ba330">EvtInterruptSynchronize</a> callback function.


### -param Context [in]

An untyped pointer to driver-supplied information that the framework passes to the <a href="https://msdn.microsoft.com/ac73b23d-7742-43a4-8950-b301bd0ba330">EvtInterruptSynchronize</a> callback function.


## -returns



<b>WdfInterruptSynchronize</b> returns the Boolean status value that the <a href="https://msdn.microsoft.com/ac73b23d-7742-43a4-8950-b301bd0ba330">EvtInterruptSynchronize</a> callback function returns.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If you want your driver to execute code that must run without being preempted and with servicing of device interrupts effectively disabled, you should place that code in an <a href="https://msdn.microsoft.com/ac73b23d-7742-43a4-8950-b301bd0ba330">EvtInterruptSynchronize</a> callback function. To schedule execution of the callback function, your driver must call <b>WdfInterruptSynchronize</b>.

The <b>WdfInterruptSynchronize</b> method returns after the <a href="https://msdn.microsoft.com/ac73b23d-7742-43a4-8950-b301bd0ba330">EvtInterruptSynchronize</a> callback function has finished executing.

Instead of calling <b>WdfInterruptSynchronize</b>, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>.

For more information about the <b>WdfInterruptSynchronize</b> method, see <a href="https://msdn.microsoft.com/a24477dc-f75d-4ab6-8695-d8a85247e276">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

For passive level interrupts, the driver must call <b>WdfInterruptSynchronize</b> at IRQL = PASSIVE_LEVEL.

Do not call <b>WdfInterruptSynchronize</b> from an arbitrary thread context,  such as a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


#### Examples

The following code example shows how to call <b>WdfInterruptSynchronize</b> to schedule execution of an <a href="https://msdn.microsoft.com/ac73b23d-7742-43a4-8950-b301bd0ba330">EvtInterruptSynchronize</a>  callback function.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN synchronizeReturnValue;

synchronizeReturnValue = WdfInterruptSynchronize(
                                         WdfInterrupt,
                                         MyEvtInterruptSynchronize,
                                         CallbackContext
                                         );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/ac73b23d-7742-43a4-8950-b301bd0ba330">EvtInterruptSynchronize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>
 

 

