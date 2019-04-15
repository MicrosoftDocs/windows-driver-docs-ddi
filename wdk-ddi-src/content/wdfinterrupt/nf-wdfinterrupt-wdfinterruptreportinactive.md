---
UID: NF:wdfinterrupt.WdfInterruptReportInactive
title: WdfInterruptReportInactive function (wdfinterrupt.h)
description: The WdfInterruptReportInactive method informs the system that the interrupt is no longer active and the driver is not expecting interrupt requests on the associated lines.
old-location: wdf\wdfinterruptreportinactive.htm
tech.root: wdf
ms.assetid: 322E70AA-5825-4199-B822-B48B12E62393
ms.date: 02/26/2018
ms.keywords: WdfInterruptReportInactive, WdfInterruptReportInactive method, kmdf._wdfinterruptreportinactive, kmdf.wdfinterruptreportinactive, wdf.wdfinterruptreportinactive, wdfinterrupt/WdfInterruptReportInactive
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfInterruptReportInactive
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptReportInactive function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   
  The <b>WdfInterruptReportInactive</b> method informs the system that the interrupt is no longer active and the driver is not expecting interrupt requests on the associated lines.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



This method does not return a value.




## -remarks



Only drivers that implement functional state power management call <b>WdfInterruptReportInactive</b>.

When a driver calls <b>WdfInterruptReportInactive</b>, the power management framework (PoFx) can then  perform related power management tasks.

Typically, a driver calls <b>WdfInterruptReportInactive</b> from either its  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a> routine, or from <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a> when <i>State</i> is greater than zero  (indicating a low-power Fx state).

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.


#### Examples

The following example shows how a driver might call <b>WdfInterruptReportInactive</b> from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a> routine of a KMDF driver. The driver registers a single component by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451097">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyComponentIdleStateCallback(
    _In_ PVOID Context,
    _In_ ULONG Component,
    _In_ ULONG State
    )
{
    PFDO_DEVICE_DATA deviceData;
    PFDO_INTERRUPT_CONTEXT interruptContext;

    deviceData = FdoGetData((WDFDEVICE)Context);
    interruptContext = InterruptGetData(deviceData-&gt;Interrupt);

    switch (State) {
        case 0:
             …
            break;

        //
        // PoFx may make us go to any of the F-states directly, hence we execute
        // F0Exit code for all of the Fx states. Note that transition to any Fx 
        // state happens from F0 (and not another Fx state).
        //
        default:
            //
            // Disable interrupt generation at hardware if needed.
            // 
            WdfInterruptAcquireLock(deviceData-&gt;Interrupt);
            DisableInterruptInHardware();
            WdfInterruptReleaseLock(deviceData-&gt;Interrupt);

            //
            // Report that interrupt is now inactive.
            //
            WdfInterruptReportInactive(deviceData-&gt;Interrupt);

            interruptContext-&gt;ReportedInactive = TRUE;

        break;

    …

}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439273">WdfInterruptReportActive</a>
 

 

