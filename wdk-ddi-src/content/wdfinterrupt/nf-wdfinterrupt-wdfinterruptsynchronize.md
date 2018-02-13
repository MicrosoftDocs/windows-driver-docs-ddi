---
UID: NF:wdfinterrupt.WdfInterruptSynchronize
title: WdfInterruptSynchronize function
author: windows-driver-content
description: The WdfInterruptSynchronize method executes a specified callback function at the device's DIRQL while holding an interrupt object's spin lock.
old-location: wdf\wdfinterruptsynchronize.htm
old-project: wdf
ms.assetid: b41fc37a-d41f-49ca-848f-844e049dd987
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfInterruptSynchronize, WdfInterruptSynchronize method, wdfinterrupt/WdfInterruptSynchronize, wdf.wdfinterruptsynchronize, DFInterruptObjectRef_d56eadd2-4636-43bb-b842-318243bcf192.xml, kmdf.wdfinterruptsynchronize, PFN_WDFINTERRUPTSYNCHRONIZE
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfInterruptSynchronize
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptSynchronize function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptSynchronize</b> method executes a specified callback function at the device's DIRQL while holding an interrupt object's spin lock.

For passive level interrupt objects, this method executes a specified callback function at passive level while holding an interrupt object's passive-level interrupt lock.


## -syntax


````
BOOLEAN WdfInterruptSynchronize(
  _In_ WDFINTERRUPT                  Interrupt,
  _In_ PFN_WDF_INTERRUPT_SYNCHRONIZE Callback,
  _In_ WDFCONTEXT                    Context
);
````


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


### -param Callback [in]

A pointer to an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a> callback function.


### -param Context [in]

An untyped pointer to driver-supplied information that the framework passes to the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a> callback function.


## -returns



<b>WdfInterruptSynchronize</b> returns the Boolean status value that the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a> callback function returns.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If you want your driver to execute code that must run without being preempted and with servicing of device interrupts effectively disabled, you should place that code in an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a> callback function. To schedule execution of the callback function, your driver must call <b>WdfInterruptSynchronize</b>.

The <b>WdfInterruptSynchronize</b> method returns after the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a> callback function has finished executing.

Instead of calling <b>WdfInterruptSynchronize</b>, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>.

For more information about the <b>WdfInterruptSynchronize</b> method, see <a href="https://msdn.microsoft.com/a24477dc-f75d-4ab6-8695-d8a85247e276">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

For passive level interrupts, the driver must call <b>WdfInterruptSynchronize</b> at IRQL = PASSIVE_LEVEL.

Do not call <b>WdfInterruptSynchronize</b> from an arbitrary thread context,  such as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


#### Examples

The following code example shows how to call <b>WdfInterruptSynchronize</b> to schedule execution of an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a>  callback function.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>



<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_synchronize.md">EvtInterruptSynchronize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptSynchronize method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

