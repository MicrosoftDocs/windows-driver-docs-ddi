---
UID: NF:wdfinterrupt.WdfInterruptReportActive
title: WdfInterruptReportActive function (wdfinterrupt.h)
description: The WdfInterruptReportActive informs the system that the interrupt is active and the driver is ready to process interrupt requests on the associated lines.
old-location: wdf\wdfinterruptreportactive.htm
tech.root: wdf
ms.assetid: 9A7B4181-0592-4C40-BC5A-99AFFA57846C
ms.date: 02/26/2018
ms.keywords: WdfInterruptReportActive, WdfInterruptReportActive method, kmdf._wdfinterruptreportactive, kmdf.wdfinterruptreportactive, wdf.wdfinterruptreportactive, wdfinterrupt/WdfInterruptReportActive
f1_keywords:
 - "wdfinterrupt/WdfInterruptReportActive"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfInterruptReportActive
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptReportActive function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   
  The <b>WdfInterruptReportActive</b> informs the system that the interrupt is active and the driver is ready to process interrupt requests on the associated lines.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -remarks



Only drivers that implement functional state power management call <b>WdfInterruptReportActive</b>.

   

A driver does not need to call <b>WdfInterruptReportActive</b> immediately after creating an interrupt.  The driver should only call <b>WdfInterruptReportActive</b> after having previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptreportinactive">WdfInterruptReportInactive</a>.

Typically, a driver calls <b>WdfInterruptReportActive</b> from either its  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a> routine, or from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a> when <i>State</i> is 0 (indicating the fully on F0 state).

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-functional-power-states">Supporting Functional Power States</a>.


#### Examples

The following example shows how a driver might call <b>WdfInterruptReportActive</b> from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a> routine of a KMDF driver. The driver registers a single component by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

```cpp
VOID
MyComponentIdleStateCallback(
    _In_ PVOID Context,
    _In_ ULONG Component,
    _In_ ULONG State
    )
{
    PFDO_DEVICE_DATA deviceData;
    PINTERRUPT_CONTEXT interruptContext;

    deviceData = FdoGetData((WDFDEVICE)Context);
    interruptContext = InterruptGetData(deviceData->Interrupt);

    switch (State) {
        case 0:
            if (interruptContext->ReportedInactive) {

                //
                // the interrupt was reported inactive earlier. We need to report active now.
                //
                WdfInterruptReportActive(deviceData->Interrupt);
                interruptContext->ReportedInactive = FALSE;

                //
                // Enable interrupt generation at hardware.
                // 
                WdfInterruptAcquireLock(deviceData->Interrupt);
                EnableInterruptInHardware();
                WdfInterruptReleaseLock(deviceData->Interrupt);

            }

        break;


    …

}

```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptreportinactive">WdfInterruptReportInactive</a>
 

 

