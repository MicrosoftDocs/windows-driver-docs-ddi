---
UID: NF:wdfinterrupt.WdfInterruptReportActive
title: WdfInterruptReportActive function
author: windows-driver-content
description: The WdfInterruptReportActive informs the system that the interrupt is active and the driver is ready to process interrupt requests on the associated lines.
old-location: wdf\wdfinterruptreportactive.htm
old-project: wdf
ms.assetid: 9A7B4181-0592-4C40-BC5A-99AFFA57846C
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFINTERRUPTREPORTACTIVE, WdfInterruptReportActive method, wdfinterrupt/WdfInterruptReportActive, kmdf.wdfinterruptreportactive, kmdf._wdfinterruptreportactive, wdf.wdfinterruptreportactive, WdfInterruptReportActive
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfInterruptReportActive
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptReportActive function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   
  The <b>WdfInterruptReportActive</b> informs the system that the interrupt is active and the driver is ready to process interrupt requests on the associated lines.


## -syntax


````
void WdfInterruptReportActive(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



This method does not return a value.




## -remarks



Only drivers that implement functional state power management call <b>WdfInterruptReportActive</b>.

   

A driver does not need to call <b>WdfInterruptReportActive</b> immediately after creating an interrupt.  The driver should only call <b>WdfInterruptReportActive</b> after having previously called <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptreportinactive.md">WdfInterruptReportInactive</a>.

Typically, a driver calls <b>WdfInterruptReportActive</b> from either its  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406416">ComponentActiveConditionCallback</a> routine, or from <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a> when <i>State</i> is 0 (indicating the fully on F0 state).

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.

For more information, see <a href="https://msdn.microsoft.com/F96214C9-702D-402E-B873-5DF57C521B34">Supporting Functional Power States</a>.


#### Examples

The following example shows how a driver might call <b>WdfInterruptReportActive</b> from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a> routine of a KMDF driver. The driver registers a single component by calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

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
    PINTERRUPT_CONTEXT interruptContext;

    deviceData = FdoGetData((WDFDEVICE)Context);
    interruptContext = InterruptGetData(deviceData-&gt;Interrupt);

    switch (State) {
        case 0:
            if (interruptContext-&gt;ReportedInactive) {

                //
                // the interrupt was reported inactive earlier. We need to report active now.
                //
                WdfInterruptReportActive(deviceData-&gt;Interrupt);
                interruptContext-&gt;ReportedInactive = FALSE;

                //
                // Enable interrupt generation at hardware.
                // 
                WdfInterruptAcquireLock(deviceData-&gt;Interrupt);
                EnableInterruptInHardware();
                WdfInterruptReleaseLock(deviceData-&gt;Interrupt);

            }

        break;


    …

}
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptreportinactive.md">WdfInterruptReportInactive</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptReportActive method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

